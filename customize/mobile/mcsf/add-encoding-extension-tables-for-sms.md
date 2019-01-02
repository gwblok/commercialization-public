---
title: Add encoding extension tables for SMS
description: Partners can extend the set of supported SMS encodings.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d1651da1-7a67-4d31-9e2d-768cb2fbebd7


ms.date: 05/02/2017
ms.topic: article


---

# Add encoding extension tables for SMS


Partners can extend the set of supported SMS encodings.

This is done by extending the following areas:

-   Set an “always-on” GSM 7-bit shift table

-   Add encoders

-   Add decoders

To add additional National Language Shift Tables to the encoding, OEMs must replace Microsoft’s SMS provider by building your own code page DLL and setting it as the default. This section contains steps that OEMs can use to build an SMS provider with custom extension tables. The OEM is responsible for testing this code and their additions to it.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
The following steps describe how to configure and build the custom encodings:

1.  Implement your code page DLL and make sure that it exports the [NlsDllCodePageTranslation](http://go.microsoft.com/fwlink/p/?LinkId=260792) function.

    > [!NOTE]
    > Ignore the note about not using the function found on the MSDN web site. This note does not apply for SMS encoding.

    When implementing your code page DLL, the DLL must have at least the following:

    -   A .def file that declares the name of the DLL—for example, `MyCodePageDLL`—and exports the **NlsDllCodePageTranslation** function:

        ```
        LIBRARY       MyCodePageDLL

        EXPORTS
            NlsDllCodePageTranslation 
        ```

    -   A .c file that defines the DLL entry point function—for example, `DllMain`—as well as the **NlsDllCodePageTranslation** function. This is the function that the APIs will call in case a particular code page value is associated with your code page DLL.

        ```
        //  NlsDllCodePageTranslation
        //
        //  This routine is the main exported procedure for the functionality in
        //  this DLL.  All calls to this DLL must go through this function.
        //
        DWORD NlsDllCodePageTranslation(
            __in DWORD CodePage,
            __in DWORD dwFlags,
            __in_ecount(cchMultiByte) LPSTR lpMultiByteStr,
            __in int cchMultiByte,
            __out_ecount(cchWideChar) LPWSTR lpWideCharStr,
            __in int cchWideChar,
            __inout LPCPINFO lpCPInfo)
        ```

    -   Inside the **NlsDllCodePageTranslation** function, you must:

        -   Make sure that the *CodePage* value is one that you expect to handle.

            -   If it is, proceed.

            -   If it is not, call `SetLastError(ERROR_INVALID_PARAMETER)` and `return 0` to exit. Returning 0 from **NlsDllCodePageTranslation** indicates to the caller that an error occurred.

    -   Switch on the `dwFlags` to handle the cases for these values (defined in winnlsp.h):

        -   NLS\_CP\_CPINFO

        -   NLS\_CP\_CPINFOEX

        -   NLS\_CP\_MBTOWC

        -   NLS\_CP\_WCTOMB

        Here's an example. Be sure to complete the items marked "OEM-TODO".

        ```
        switch (dwFlags & 0xF0000000) // only look at the highest nibble
        {
            case (NLS_CP_CPINFO):
            {
                if (lpCPInfo == NULL)    
                {
                   SetLastError(ERROR_INVALID_PARAMETER);
                   return (0);
                }
                memset(lpCPInfo, 0, sizeof(CPINFO));

                // OEM-TODO: fill other parts of the CPINFO structure as needed, 
                // with one requirement for our test code: 
                lpCPInfo->DefaultChar[0] = 0x20;
                return (TRUE);
            }
            break;

            case (NLS_CP_CPINFOEX): // this is actually optional
            {
                if (lpCPInfo == NULL)    
                {
                   SetLastError(ERROR_INVALID_PARAMETER);
                   return (0);
                }
                memset(lpCPInfo, 0, sizeof(CPINFOEX));

                // OEM-TODO: fill other parts of the CPINFO structure as needed, 
                // with one requirement for our test code: 
                lpCPInfo->DefaultChar[0] = 0x20;
                return (TRUE);
            }  
            break;

            case ( NLS_CP_MBTOWC ) :
            {
                // ensure unsupported flag combinations are not passed in
                if (dwFlags & ~(NLS_CP_MBTOWC | MB_ERR_INVALID_CHARS))
                {
                   // other flags not allowed
                   SetLastError(ERROR_INVALID_FLAGS);
                   return (0);
                }

                // if caller expects us to figure out the input string length, do it now
                if (cchMultiByte == -1)
                {
                   // see if the string is too long
                   if (FAILED(StringCchLengthA(lpMultiByteStr, STRSAFE_MAX_CCH, (size_t *)&cchMultiByte)))
                   {
                       SetLastError(ERROR_INVALID_PARAMETER);
                       return (0);
                   }
                   // add one for the NULL terminator
                   cchMultiByte += 1;
                }

                // OEM-TODO: convert lpMultiByteStr to lpWideCharStr according to own 
                // conversion table, taking into account: 
                // * dwFlags & MB_ERR_INVALID_CHARS (preserve MB_ERR_INVALID_CHARS flag 
                //      in case the caller wants to error out on invalid input characters)
                // * cchWideChar – if cchWideChar == 0 or lpWideCharStr == NULL, that 
                //      means the caller just wants to know how big lpWideCharStr should be

                return  (the number of characters in converted lpWideCharStr + 1 for the NULL terminator);
            } 
            break;

            case ( NLS_CP_WCTOMB ) :
            {
                // ensure unsupported flag combinations are not passed in
                if (dwFlags & ~(NLS_CP_WCTOMB | WC_ERR_INVALID_CHARS))
                {
                    // other flags not allowed
                    SetLastError(ERROR_INVALID_FLAGS);
                    return (0);
                }

                // if caller expects us to figure out the input string length, do it now
                if (cchWideChar == -1)
                {
                   // see if the string is too long
                   if (FAILED(StringCchLengthW(lpWideCharStr, STRSAFE_MAX_CCH, (size_t *)&cchWideChar)))
                   {
                       SetLastError(ERROR_INVALID_PARAMETER);
                       return (0);
                   }
                   // add one for the NULL terminator
                   cchWideChar += 1;
               }
                // OEM-TODO: convert lpWideCharStr to lpMultiByteStr according to own
                // conversion table, taking into account: 
                // * dwFlags & MB_ERR_INVALID_CHARS (preserve MB_ERR_INVALID_CHARS flag 
                //      in case the caller wants to error out on invalid input characters)
                // * cchMultiByte – if cchMultiByte == 0 or lpMultiByteStr == NULL, that 
                //      means the caller just wants to know how big lpMultiByteStr should be

                return (the number of characters in converted lpMultiByteStr + 1 for the NULL terminator);
            } 
            break;
        } 
        //
        //  if we haven't returned out of this function yet, the caller passed in an invalid flag
        //
        SetLastError(ERROR_INVALID_FLAGS);
        return (0);
        }
        // end of NlsDllCodePageTranslation function
        ```

2.  Pick a code page ID in the range 55050–55099.

    Here are the code page identifiers for the new supported SMS encodings in Windows 10 Mobile as well as the reserved ranges to be used for future SMS encodings:

    | NLS code page ID | Description                              |
    |:-----------------|:-----------------------------------------|
    | 55000            | GSM 7-bit                                |
    | 55001            | GSM with Single Shift for Spanish        |
    | 55002            | GSM with Single Shift for Portuguese     |
    | 55003            | GSM with Single Shift for Turkish        |
    | 55004            | SMS Greek Reduction                      |
    | 55005–55049      | Reserved                                 |
    | **55050–55099**  | Available for OEM-supplied SMS encodings |

3.  Add your code page DLL to the device. To do this, set the **CodepageDLL** asset source to the location and file name of your code page DLL. For example:

    ```
          <Asset Name="CodePageDLL" Source="C:\OEMCodePages\CodePage55050.dll" />
    ```

4.  Register your DLL with NLS by setting the corresponding `EncodingCodePages/CodepageID550XX` setting.

    For example, if the DLL is `Codepage55050.dll`, set `EncodingCodePages/CodepageID55050` as shown in the following example:

    ```
          <Setting Name="EncodingCodePages/CodepageID55050" Value="CodePage55050.dll" />
    ```

5.  Add the registered codepages to the custom OEM package as described in [SMS encoding](sms-encoding.md).

    Alternatively, you can write a settings app that dynamically sets the registry values depending on the user-selected encoding scheme. For example, if the OEM app sets the encoding to 55050, set the `Encodings/GSM7BitEncodingPage` setting and reboot the device.

    ```
          <Setting Name="Encodings/GSM7BitEncodingPage" Value="55050" />
    ```

<a href="" id="testing-steps-"></a>**Testing steps:**  
Work with your mobile operator to test this customization on their network.
