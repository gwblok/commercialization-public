---

Description: Add languages to an offline Windows image
ms.assetid: 128cffa3-8c53-41c8-add2-fa10197f36a3
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Add languages to Windows images

ms.date: 11/27/2018
ms.topic: article
redirect_url: https://docs.microsoft.com/windows-hardware/manufacture/desktop/add-language-packs-to-windows
ms.custom: RS5
---

# Add languages to an offline Windows image 

> [!note]
> To add a language to your personal PC, go to **Settings** > **Time & Language** > **Language**, and choose a language to install. [Learn more](https://support.microsoft.com/en-us/help/4027670/windows-10-add-and-switch-input-and-display-language-preferences)

Add languages and regional support to your offline mounted Windows 10 or Windows Server images. 

To learn about languages and components, see [Add languages to Windows](add-language-packs-to-windows.md). 

In this example, we'll install the French language, and then add a LIP language (Luxembourgish) that uses French for its base language.

To add a language to an offline image, you'll need the following:

- Language Pack ISO
- Feature on Demand ISO
- A Windows image

See [Add languages to Windows: Where to get language packs](add-language-packs-to-windows.md#get-languages) to find out where you can get these ISOs.

### Mount Windows and Windows RE images (if you're adding a language to an offline image)

-   Mount the Windows and Windows RE images. The Windows RE image file is part of the Windows image:

    ```
    md C:\mount\windows
    Dism /Mount-Image /ImageFile:install.wim /Index:1 /MountDir:"C:\mount\windows"
    md C:\mount\winre
    Dism /Mount-Image /ImageFile:"C:\mount\windows\Windows\System32\Recovery\winre.wim" /index:1 /MountDir:"C:\mount\winre"
    ```

    See [Mount and modify an image using DISM](mount-and-modify-a-windows-image-using-dism.md) to learn more about mounting an image.

### Add a language to Windows

Preinstall languages by adding the language packs and their related Features on Demand for all preinstalled languages, including the base languages if you're adding a LIP language.

If you're adding a language to an online image, the process is the same, but use `/online` instead of `/Image:<pathtoimage>` in your DISM commands.

1.  Mount the language pack and FOD ISOs with File explorer. This will assign them drive letters.

2.  Add the language pack to Windows. Use `dism /Add-Package` to add the language pack.

    ```
    Dism /Add-Package /Image:"C:\mount\windows" /PackagePath="D:\x64\langpacks\Microsoft-Windows-Client-Language-Pack_x64_fr-fr.cab"
    ```

    Where D:\ is the Language pack ISO 

3.  Add the language FODs. Always preinstall the Basic, Fonts, OCR, Text-to-speech, and Speech recognition FODs if they're available for the languages you’re preinstalling. Additionally, preinstall the handwriting language component FOD if you’re shipping a device with a pen.
    
    See [Features on demand](features-on-demand-v2--capabilities.md) to can learn more about FODs, including details on adding them to a Windows image.

    ```
    Dism /Image:"C:\mount\windows" /Add-Package /PackagePath:E:\Microsoft-Windows-LanguageFeatures-Basic-fr-fr-Package~31bf3856ad364e35~amd64~~.cab /PackagePath:E:\Microsoft-Windows-LanguageFeatures-OCR-fr-fr-Package~31bf3856ad364e35~amd64~~.cab /PackagePath:E:\Microsoft-Windows-LanguageFeatures-Handwriting-fr-fr-Package~31bf3856ad364e35~amd64~~.cab /PackagePath:E:\Microsoft-Windows-LanguageFeatures-TextToSpeech-fr-fr-Package~31bf3856ad364e35~amd64~~.cab /PackagePath:E:\Microsoft-Windows-LanguageFeatures-Speech-fr-fr-Package~31bf3856ad364e35~amd64~~.cab
    ```

    Where E:\ is the Features on demand ISO.

4.  After adding the language pack, verify that it's in the images.

    ```
    Dism /Image:"C:\mount\windows" /Get-packages
    Dism /Image:"C:\mount\windows" /Get-capabilities
    ```

4.  Add any other capabilities, such as fonts, required for that region. To learn about additional FODs, see, see [Language and region features On Demand](features-on-demand-non-language-fod.md).

    ```
    rem Thai example (add th-TH first).
    Dism /Image:"C:\mount\windows" Add-capability /capabilityname:Language.Fonts.Thai~~~und-THAI~0.0.1.0 /source:E:
    Dism /Get-Capabilities /Image:"C:\mount\windows"
    ```
5.  **If you're adding a LIP language** Add your LIP language that uses the language that we just added (fr-FR) as a base language. Not all LIP languages have all language components. Luxembourgish (lb-LU), for example, only has basic and handwriting FODs. You can learn which FODs are available for languages [in the LP to FOD mapping spreadsheet](http://download.microsoft.com/download/C/6/C/C6C91D1F-F96A-40FA-AF9D-E73FA4EAD344/Windows-10-1809-FOD-to-LP-Mapping-Table.xlsx)

    1. Add the LIP, which is on the language pack ISO in the LXP folder. This type of language pack is distributed as an .appx.
        
        ```
        DISM /Image:"C:\mount\windows" /add-provisionedappxpackage /PackagePath="D:\LocalExperiencePack\lb-lu\LanguageExperiencePack.lb-LU.Neutral.appx /licensepath:"D:\LocalExperiencePack\lb-lu\License.xml"
        ```
    
        Where D:\ is the language pack ISO
    
    2. Add the features on demand that support your LIP language.
    
        ```
        DISM /Image:"C:\mount\windows" /Add-Package /PackagePath:E:\Microsoft-Windows-LanguageFeatures-Basic-lb-lu-Package~31bf3856ad364e35~amd64~~.cab /PackagePath:E:\Microsoft-Windows-LanguageFeatures-Handwriting-lb-lu-Package~31bf3856ad364e35~amd64~~.cab
        ```
        
        Where E:\ is the Feature on Demand ISO

    3. Verify that the LIP is in the image

        ```
        DISM /Image:"C:\mount\windows" get-provisionedappxpackages
        ```

6.  When you add languages to Windows, when possible, add them to WinRE to ensure a consistent language experience in recovery scenarios.These language packs are also available on the Language pack ISO. Windows RE requires the WinPE-HTA package.

    ```
    Dism /Image:C:\mount\winre /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\lp.cab"
    Dism /Image:C:\mount\winre /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-Rejuv_fr-fr.cab"
    Dism /Image:C:\mount\winre /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-EnhancedStorage_fr-fr.cab"
    Dism /Image:C:\mount\winre /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-Scripting_fr-fr.cab"
    Dism /Image:C:\mount\winre /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-SecureStartup_fr-fr.cab"
    Dism /Image:C:\mount\winre /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-SRT_fr-fr.cab"
    Dism /Image:C:\mount\winre /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-WDS-Tools_fr-fr.cab"
    Dism /Image:C:\mount\winre /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-WMI_fr-fr.cab"
    Dism /Image:C:\mount\winre /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-StorageWMI_fr-fr.cab"
    Dism /Image:C:\mount\winre /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-HTA_fr-fr.cab"
    ```

7.  After adding the packages, verify that they're in the image.

    ```
    Dism /Get-Packages /Image:"C:\mount\winre"
    ```
    Example output from /Get-Packages: 

    ```
    Package Identity : Microsoft-Windows-WinPE-Rejuv_fr-fr ... fr-FR~10.0.9926.0 State : Installed
    ```

## Remove a language

Before you add new language packs to a Windows image, you must remove any language packs that you don't intend to use. There are two ways to remove language packs offline with DISM. You can either apply an unattended answer file to the offline image, or you can remove the language pack directly from the offline image, using the command prompt.

If you're removing a language from an online image, the process is the same, but use `/online` instead of `/Image:<pathtoimage>` in your DISM commands.

> [!important]
> You cannot remove a language pack from an offline Windows image if there are pending online actions. The Windows image should be a recently installed and captured image. This will guarantee that the Windows image does not have any pending online actions that require a reboot.


### Remove a language from a Windows image

> [!note]
> If you're adding a language to an online image, the process is the same, but use `/online` instead of `/Image:<pathtoimage>` in your DISM commands.

1.  Locate the Windows image (.wim) file or virtual hard disk (.vhd or .vhdx) that contains the Windows image that you intend to remove languages from.

2.  Open a Command prompt as administrator.

3.  Mount a Windows image if you want to remove languages from an offline image.

    ```
    Dism /Mount-Image /ImageFile:C:\test\images\install.wim /MountDir:C:\test\offline
    ```

4.  Get a list of packages that are installed on your mounted image.

    ```
    Dism /Image:C:\test\offline /Get-Packages
    ```

5. **If removing a LIP language** Use DISM to remove the LIP .appx

    ```
    Dism /Image:C:\test\offline  /remove-provisionedappxpackage /packagename:Microsoft.LanguageExperiencePack<lang_version>_neutral__8wekyb3d8bbwe
    ```

6.  Use `DISM /remove-package /packagename:<packagename>` to remove language components from the image. Use the packages names that you got in step 5. You can specify more than one `/packagename` per command-line statement.

    ```
    Dism /Image:C:\test\offline /Remove-Package /PackageName:<language pack name> /PackageName:<language component package Name>  ...
    ```

7.  Commit the changes. The image remains mounted until you run `DISM /unmount`.

    ```
    Dism /Commit-Image /MountDir:C:\test\offline
    ```


## Next steps: Configure international settings

After you add or remove a language pack in a Windows image, you can set the default user interface (UI) language, which is also known as the display language. At the same time, you can configure the international settings in the Windows image.

> [!Note]
> If you specify a default UI language and locale settings with the DISM tool, and then specify different language and locale settings in an answer file, the settings in the answer file overwrite the default values specified by the DISM tool.

See [Configure international settings by using DISM](configure-international-settings-in-windows.md).

## <span id="related_topics"></span>Related topics

[Add Language Packs to Windows](add-language-packs-to-windows.md)

[DISM - Deployment Image Servicing and Management Technical Reference for Windows](dism---deployment-image-servicing-and-management-technical-reference-for-windows.md)

[DISM Languages and International Servicing Command-Line Options](dism-languages-and-international-servicing-command-line-options.md)

