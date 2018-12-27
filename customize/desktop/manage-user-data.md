---
title: Protect and collect user data
description: Generate a public/private key pair for customer data encryption and decryption.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 01/25/2018
ms.topic: article


---
# Protect and collect user data

If a customer enters information into the OEM registration pages, the following files are created when they complete OOBE:

* **Userdata.blob**. An encrypted XML file that contains all the values in all user-configurable elements on the registration pages, including customer information fields and checkbox states.
* **SessionKey.blob**. Generated during encryption of Userdata.blob. Contains a session key needed for the decryption process.
* **Userchoices.xml**. An un-encrypted XML file that contains the checkbox labels and values for all checkboxes included on the registration pages.

> [!Note]
> If a customer clicks `Skip` on the first registration page, no data is written or stored to these files, not even the checkbox default states.

The timestamp of the user's out of box experience is also added to the Windows registry under this key:

`HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE\Stats [EndTimeStamp]`

This registry value is created regardless of whether the registration pages are included in OOBE. The timestamp is written in UTC (Coordinated Universal Time) format; specifically, it is a `SYSTEMTIME` value written as a serialized blob of data to the registry.

In order for you to access and use the customer information, take the following steps:

1. [Generate a public/private key pair](#generate-a-publicprivate-key-pair), and place the public key in the `%systemroot%\system32\Oobe\Info` folder of the image.
1. [Collect the encrypted customer data](#collect-encrypted-customer-data) using an app or a service that runs roughly 30 minutes after the first logon completes.
1. [Send the data to your server for decryption](#send-data-to-your-server-for-decryption) using SSL. You can then decrypt the session key to decrypt the customer data.

## Generate a public/private key pair

To protect customer data, you must generate a public/private key pair, and the public key must be placed in the `%systemroot%\system32\Oobe\Info` folder. If you’re deploying images to multiple regions or in multiple languages, you should put the public key directly under region and language-specific subdirectories, following the same rules as you would for region or language-specific Oobe.xml files as described in [How Oobe.xml works](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/how-oobexml-works).

> [!Important]
> You must never place the private key on the customer's PC. Instead, it should be stored securely on your servers so the data can be decrypted after it's uploaded. If a customer clicks Next on the Registration pages, Windows uses the public key to create Sessionkey.blob in the `%systemroot%\system32\Oobe\Info` folder. Your service or Microsoft Store app should upload the data to your server by using SSL. You then need to decrypt the session key to decrypt the customer data.

If there’s no public key in the `%systemroot%\system32\Oobe\Info` folder, the registration pages aren’t shown.

### Generate public and private keys

Make this sequence of calls to generate the public and private keys.

1. Acquire crypt context using the [CryptAcquireContext API](https://msdn.microsoft.com/en-us/library/windows/desktop/aa379886%28v=vs.85%29.aspx(d=robot)). Provide these values:

    * `pszProvider` is `MS_ENH_RSA_AES_PROV`
    * `dwProvType` is `PROV_RSA_AES`

1. Generate RSA crypt key using the [CryptGenKey API](https://msdn.microsoft.com/en-us/library/windows/desktop/aa379941%28v=vs.85%29.aspx(d=robot)). Provide these values:

    * `Algid` is `CALG_RSA_KEYX`
    * `dwFlags` is `CRYPT_EXPORTABLE`

1. Serialize the public key portion of the crypt key from Step 2 using the [CryptExportKey API](https://msdn.microsoft.com/en-us/library/windows/desktop/aa379931%28v=vs.85%29.aspx). Provide this value:

    * `dwBlobType` is `PUBLICKEYBLOB`

1. Write the serialized public key bytes from Step 3 to file Pubkey.blob using the standard [Windows File Management functions](https://msdn.microsoft.com/en-us/library/windows/desktop/aa364232(v=vs.85).aspx(d=robot)).
1. Serialize the private key portion of the crypt key from Step 2 using the [CryptExportKey API](https://msdn.microsoft.com/en-us/library/windows/desktop/aa379931%28v=vs.85%29.aspx). Provide this value

    * `dwBlobType` is `PRIVATEKEYBLOB`

1. Write the serialized private key bytes from step 5 to file Prvkey.blob using the standard Windows File API.

### Code snippet

This code snippet shows how to generate the keys:

```C++
HRESULT CryptExportKeyHelper(_In_ HCRYPTKEY hKey, _In_opt_ HCRYPTKEY hExpKey, DWORD dwBlobType, _Outptr_result_bytebuffer_(*pcbBlob) BYTE **ppbBlob, _Out_ DWORD *pcbBlob);

HRESULT WriteByteArrayToFile(_In_ PCWSTR pszPath, _In_reads_bytes_(cbData) BYTE const *pbData, DWORD cbData);

// This method generates an OEM public and private key pair and writes it to Pubkey.blob and Prvkey.blob
HRESULT GenerateKeysToFiles()
{
    // Acquire crypt provider. Use provider MS_ENH_RSA_AES_PROV and provider type PROV_RSA_AES to decrypt the blob from OOBE.
    HCRYPTPROV hProv;
    HRESULT hr = CryptAcquireContext(&hProv, L"OEMDecryptContainer", MS_ENH_RSA_AES_PROV, 
PROV_RSA_AES, CRYPT_NEWKEYSET) ? S_OK : HRESULT_FROM_WIN32(GetLastError());
    if (hr == NTE_EXISTS)
    {
        hr = CryptAcquireContext(&hProv, L"OEMDecryptContainer", MS_ENH_RSA_AES_PROV, 
PROV_RSA_AES, 0) ? S_OK : HRESULT_FROM_WIN32(GetLastError());
    }

    if (SUCCEEDED(hr))
    {
        // Call CryptGenKey to generate the OEM public and private key pair. OOBE expects the algorithm to be CALG_RSA_KEYX.
        HCRYPTKEY hKey;
        hr = CryptGenKey(hProv, CALG_RSA_KEYX, CRYPT_EXPORTABLE, &hKey) ? S_OK : HRESULT_FROM_WIN32(GetLastError());
        if (SUCCEEDED(hr))
        {
            // Call CryptExportKeyHelper to serialize the public key into bytes.
            BYTE *pbPubBlob;
            DWORD cbPubBlob;
            hr = CryptExportKeyHelper(hKey, NULL, PUBLICKEYBLOB, &pbPubBlob, &cbPubBlob);
            if (SUCCEEDED(hr))
            {
                // Call CryptExportKey again to serialize the private key into bytes.
                BYTE *pbPrvBlob;
                DWORD cbPrvBlob;
                hr = CryptExportKeyHelper(hKey, NULL, PRIVATEKEYBLOB, &pbPrvBlob, &cbPrvBlob);
                if (SUCCEEDED(hr))
                {
                    // Now write the public key bytes into the file pubkey.blob
                    hr = WriteByteArrayToFile(L"pubkey.blob", pbPubBlob, cbPubBlob);
                    if (SUCCEEDED(hr))
                    {
                        // And write the private key bytes into the file Prvkey.blob
                        hr = WriteByteArrayToFile(L"prvkey.blob", pbPrvBlob, cbPrvBlob);
                    }
                    HeapFree(GetProcessHeap(), 0, pbPrvBlob);
                }
                HeapFree(GetProcessHeap(), 0, pbPubBlob);
            }
            CryptDestroyKey(hKey);
        }
        CryptReleaseContext(hProv, 0);
    }
    return hr;
}

HRESULT CryptExportKeyHelper(_In_ HCRYPTKEY hKey, _In_opt_ HCRYPTKEY hExpKey, DWORD dwBlobType, _Outptr_result_bytebuffer_(*pcbBlob) BYTE **ppbBlob, _Out_ DWORD *pcbBlob)
{
    *ppbBlob = nullptr;
    *pcbBlob = 0;

    // Call CryptExportKey the first time to determine the size of the serialized key.
    DWORD cbBlob = 0;
    HRESULT hr = CryptExportKey(hKey, hExpKey, dwBlobType, 0, nullptr, &cbBlob) ? S_OK : HRESULT_FROM_WIN32(GetLastError());
    if (SUCCEEDED(hr))
    {
        // Allocate a buffer to hold the serialized key.
        BYTE *pbBlob = reinterpret_cast<BYTE *>(CoTaskMemAlloc(cbBlob));
        hr = (pbBlob != nullptr) ? S_OK : E_OUTOFMEMORY;
        if (SUCCEEDED(hr))
        {
            // Now export the key to the buffer.
            hr = CryptExportKey(hKey, hExpKey, dwBlobType, 0, pbBlob, &cbBlob) ? S_OK : HRESULT_FROM_WIN32(GetLastError());
            if (SUCCEEDED(hr))
            {
                *ppbBlob = pbBlob;
                *pcbBlob = cbBlob;
                pbBlob = nullptr;
            }
            CoTaskMemFree(pbBlob);
        }
    }
    return hr;
}

HRESULT WriteByteArrayToFile(_In_ PCWSTR pszPath, _In_reads_bytes_(cbData) BYTE const *pbData, DWORD cbData)
{
    bool fDeleteFile = false;
    HANDLE hFile = CreateFile(pszPath, GENERIC_WRITE, 0, nullptr, CREATE_ALWAYS, FILE_ATTRIBUTE_NORMAL, nullptr);
    HRESULT hr = (hFile == INVALID_HANDLE_VALUE) ? HRESULT_FROM_WIN32(GetLastError()) : S_OK;
    if (SUCCEEDED(hr))
    {
        DWORD cbWritten;
        hr = WriteFile(hFile, pbData, cbData, &cbWritten, nullptr) ? S_OK : HRESULT_FROM_WIN32(GetLastError());
        fDeleteFile = FAILED(hr);
        CloseHandle(hFile);
    }

    if (fDeleteFile)
    {
        DeleteFile(pszPath);
    }
    return hr;
}
```

## Collect encrypted customer data

Create and preinstall a Microsoft Store app, or write a service to run after first sign-in, to:

1. Collect the encrypted customer data, including the user name from the [Windows.System.User namespace](https://docs.microsoft.com/en-us/uwp/api/windows.system.user), as well as the local time stamp of first sign-in.
1. Upload that data set to your server for decryption and use.

To use a Microsoft Store app to collect the data, assign its Application User Model ID (AUMID) to the [Microsoft-Windows-Shell-Setup | OOBE | OEMAppId](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/unattend/microsoft-windows-shell-setup-oobe-oemappid) Unattend setting. Windows will pass the timestamp, user data, session key, and checkbox state data to the application data folder for the OEM app, that is associated with the first user to logon to the device. For example, `%localappdata%\packages\[OEM app package family name]\LocalState` for that user.

If you create and run a service to upload the data, you should set the service to run at least 30 minutes after the user gets to the Start screen, and only run the service once. Setting your service to run at this time ensures that your service won't consume system resources in the background while users are getting their first chance to explore the Start screen and their apps. The service must gather the data from within the OOBE directory, as well as the time stamp and user name, as applicable. The service should also determine what actions to take in response to the user's choices. For example, if the user opted in to an anti-malware app trial, your service should start the trial rather than rely on the anti-malware app to decide if it should run. Or, as another example, if your user opted in to emails from your company or partner companies, your service should communicate that info to whomever handles your marketing emails.

For more info about how to write a service, see [Developing Windows Service Applications](https://docs.microsoft.com/en-us/dotnet/framework/windows-services/index).

## Send data to your server for decryption

Your service or Microsoft Store app should upload the data to your server using SSL. You then need to decrypt the session key to decrypt the customer data.

### Decrypt the data

Make this sequence of calls to decrypt the data:

1. Acquire crypt context by using the [CryptAcquireContext API](https://msdn.microsoft.com/en-us/library/windows/desktop/aa379886(v=vs.85).aspx). Provide these values:

    * `pszProvider` is `MS_ENH_RSA_AES_PROV`
    * `dwProvType` is `PROV_RSA_AES`

1. Read the OEM private key file (Prvkey.blob) from disk using the standard Windows File API.
1. Convert the private key bytes into a crypt key using the [CryptImportKey API](https://msdn.microsoft.com/en-us/library/windows/desktop/aa380207(v=vs.85).aspx).
1. Read the OOBE-generated session key file (**Sessionkey.blob**) from disk using the standard Windows File API.
1. Use the private key from Step 3 to convert the session key bytes into a crypt key, using the [CryptImportKey API](https://msdn.microsoft.com/en-us/library/windows/desktop/aa380207(v=vs.85).aspx).
1. Export key (hPubKey) is the private key imported in Step 3.
1. Read OOBE-written encrypted user data (**Userdata.blob**) from disk using the standard Windows File API.
1. Use session key (from Step 5) to decrypt the user data, using [CryptDecrypt](https://msdn.microsoft.com/en-us/library/windows/desktop/aa379913(v=vs.85).aspx).

### Code snippet

This code snippet shows how to decrypt the data:

```c++
HRESULT DecryptHelper(_In_reads_bytes_(cbData) BYTE *pbData, DWORD cbData, _In_ HCRYPTKEY hPrvKey, _Outptr_result_bytebuffer_(*pcbPlain) BYTE **ppbPlain, _Out_ DWORD *pcbPlain);
HRESULT ReadFileToByteArray(_In_ PCWSTR pszPath, _Outptr_result_bytebuffer_(*pcbData) BYTE **ppbData, _Out_ DWORD *pcbData);

// This method uses the specified Userdata.blob (pszDataFilePath), Sessionkey.blob (pszSessionKeyPath), and Prvkey.blob (pszPrivateKeyPath)
// and writes the plaintext XML user data to Plaindata.xml
HRESULT UseSymmetricKeyFromFileToDecrypt(_In_ PCWSTR pszDataFilePath, _In_ PCWSTR pszSessionKeyPath, _In_ PCWSTR pszPrivateKeyPath)
{
    // Acquire crypt provider. Use provider MS_ENH_RSA_AES_PROV and provider type PROV_RSA_AES to decrypt the blob from OOBE.
    HCRYPTPROV hProv;
    HRESULT hr = CryptAcquireContext(&hProv, L"OEMDecryptContainer", MS_ENH_RSA_AES_PROV, PROV_RSA_AES, CRYPT_NEWKEYSET) ? S_OK : HRESULT_FROM_WIN32(GetLastError());
    if (hr == NTE_EXISTS)
    {
        hr = CryptAcquireContext (&hProv, L"OEMDecryptContainer", MS_ENH_RSA_AES_PROV, PROV_RSA_AES, 0) ? S_OK : HRESULT_FROM_WIN32(GetLastError());
    }

    if (SUCCEEDED(hr))
    {
        // Read in the OEM private key file.
        BYTE *pbPrvBlob;
        DWORD cbPrvBlob;
        hr = ReadFileToByteArray(pszPrivateKeyPath, &pbPrvBlob, &cbPrvBlob);
        if (SUCCEEDED(hr))
        {
            // Convert the private key file bytes into an HCRYPTKEY.
            HCRYPTKEY hKey;
            hr = CryptImportKey(hProv, pbPrvBlob, cbPrvBlob, 0, 0, &hKey) ? S_OK : HRESULT_FROM_WIN32(GetLastError());
            if (SUCCEEDED(hr))
            {
                // Read in the encrypted session key generated by OOBE.
                BYTE *pbSymBlob;
                DWORD cbSymBlob;
                hr = ReadFileToByteArray(pszSessionKeyPath, &pbSymBlob, &cbSymBlob);
                if (SUCCEEDED(hr))
                {
                    // Convert the encrypted session key file bytes into an HCRYPTKEY.
                    // This uses the OEM private key to decrypt the session key file bytes.
                    HCRYPTKEY hSymKey;
                    hr = CryptImportKey(hProv, pbSymBlob, cbSymBlob, hKey, 0, &hSymKey) ? S_OK : HRESULT_FROM_WIN32(GetLastError());
                    if (SUCCEEDED(hr))
                    {
                        // Read in the encrypted user data written by OOBE.
                        BYTE *pbCipher;
                        DWORD dwCipher;
                        hr = ReadFileToByteArray(pszDataFilePath, &pbCipher, &dwCipher);
                        if (SUCCEEDED(hr))
                        {
                            // Use the session key to decrypt the encrypted user data.
                            BYTE *pbPlain;
                            DWORD dwPlain;
                            hr = DecryptHelper(pbCipher, dwCipher, hSymKey, &pbPlain, &dwPlain);
                            if (SUCCEEDED(hr))
                            {
                                hr = WriteByteArrayToFile(L"plaindata.xml", pbPlain, dwPlain);
                                HeapFree(GetProcessHeap(), 0, pbPlain);
                            }
                            HeapFree(GetProcessHeap(), 0, pbCipher);
                        }
                        CryptDestroyKey(hSymKey);
                    }
                    HeapFree(GetProcessHeap(), 0, pbSymBlob);
                }
                else if (hr == HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND))
                {
                    wcout << L"Couldn't find session key file [" << pszSessionKeyPath << L"]" << endl;
                }
                CryptDestroyKey(hKey);
            }
            HeapFree(GetProcessHeap(), 0, pbPrvBlob);
        }
        else if (hr == HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND))
        {
            wcout << L"Couldn't find private key file [" << pszPrivateKeyPath << L"]" << endl;
        }
        CryptReleaseContext(hProv, 0);
    }
    return hr;
}

HRESULT DecryptHelper(_In_reads_bytes_(cbData) BYTE *pbData, DWORD cbData, _In_ HCRYPTKEY hPrvKey, _Outptr_result_bytebuffer_(*pcbPlain) BYTE **ppbPlain, _Out_ DWORD *pcbPlain)
{
        BYTE *pbCipher = reinterpret_cast<BYTE *>(HeapAlloc(GetProcessHeap(), 0, cbData));
    HRESULT hr = (pbCipher != nullptr) ? S_OK : E_OUTOFMEMORY;
    if (SUCCEEDED(hr))
    {
        // CryptDecrypt will write the actual length of the plaintext to cbPlain.
        // Any block padding that was added during CryptEncrypt won't be counted in cbPlain.
        DWORD cbPlain = cbData;
        memcpy(pbCipher, pbData, cbData);
        hr = ResultFromWin32Bool(CryptDecrypt(hPrvKey, 
                                              0, 
                                              TRUE, 
                                              0,
                                              pbCipher, 
                                              &cbPlain));
        if (SUCCEEDED(hr))
        {
            *ppbPlain = pbCipher;
            *pcbPlain = cbPlain;
            pbCipher = nullptr;
        }
        HeapFree(GetProcessHeap(), 0, pbCipher);
    }    return hr;
}

HRESULT ReadFileToByteArray(_In_ PCWSTR pszPath, _Outptr_result_bytebuffer_(*pcbData) BYTE **ppbData, _Out_ DWORD *pcbData)
{
    *ppbData = nullptr;
    *pcbData = 0;
    HANDLE hFile = CreateFile(pszPath, GENERIC_READ, 0, nullptr, OPEN_EXISTING, FILE_ATTRIBUTE_NORMAL, nullptr);
    HRESULT hr = (hFile == INVALID_HANDLE_VALUE) ? HRESULT_FROM_WIN32(GetLastError()) : S_OK;
    if (SUCCEEDED(hr))
    {
        DWORD cbSize = GetFileSize(hFile, nullptr);
        hr = (cbSize != INVALID_FILE_SIZE) ? S_OK : ResultFromKnownLastError();
        if (SUCCEEDED(hr))
        {
            BYTE *pbData = reinterpret_cast<BYTE *>(CoTaskMemAlloc(cbSize));
            hr = (pbData != nullptr) ? S_OK : E_OUTOFMEMORY;
            if (SUCCEEDED(hr))
            {
                DWORD cbRead;
                hr = ReadFile(hFile, pbData, cbSize, &cbRead, nullptr) ? S_OK : HRESULT_FROM_WIN32(GetLastError());
                if (SUCCEEDED(hr))
                {
                    *ppbData = pbData;
                    *pcbData = cbSize;
                    pbData = nullptr;
                }
                CoTaskMemFree(pbData);
            }
        }
        CloseHandle(hFile);
    }
    return hr;
}
```
