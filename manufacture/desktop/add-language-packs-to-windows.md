---

Description: Add languages to Windows images
ms.assetid: 128cffa3-8c53-41c8-add2-fa10197f36a3
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Add languages to Windows images

ms.date: 11/27/2018
ms.topic: article
ms.custom: RS5
---

# Add languages to Windows images

> [!note]
> To add a language to your personal PC, go to **Settings** > **Time & Language** > **Language**, and choose a language to install. [Learn more](https://support.microsoft.com/en-us/help/4027670/windows-10-add-and-switch-input-and-display-language-preferences)

You can add languages and regional support to Windows 10 (except for Windows 10 Home Single Language and Windows 10 Home Country Specific editions), and Windows Server.

Windows installations start with at least one language pack and its language components. You can add: 
* [Language packs](available-language-packs-for-windows.md): Localization packages for Windows, delivered as a .cab file, for example, Microsoft-Windows-Client-Language-Pack_x64_es-es.cab. Includes UI elements like text for dialog boxes, menu items, and help files.
* [Language Interface Packs (LIPs)](available-language-packs-for-windows.md#lips): Partially-localized language pack. Requires a base language pack. In Windows 10, version 1809, LIPs are delivered as Local Experience Packs (LXPs) .appx files, for example, LanguageExperiencePack.am-et.neutral.appx. For previous versions of Windows 10, LIPs are delivered as .cab files, for example, C:\Languages\es-ES\lp.cab.
* [Features On Demand](features-on-demand-language-fod.md): Features include language basics (like spell checking), fonts, optical character recognition, handwriting, text-to-speech, and speech recognition. You can save disk space by choosing not to include some language components in your image. While this reduction in image size can be helpful when creating images for lower-cost devices with small storage, it does lead to an incomplete language experience.  Delivered as .cab files, for example, Microsoft-Windows-LanguageFeatures-Basic-fr-fr-Package.
* [Recovery languages](customize-windows-re.md): UI text for the Windows Recovery Environment (WinRE). Delivered as .cab files. Example: lp.cab, WinPE-Rejuv_fr-fr.cab, and more.

## <span id="get-languages"></span>Get language resources: Language Pack ISO and Feature on Demand ISO

-   **OEMs and System Builders** with Microsoft Software License Terms can download the Language Pack ISO and Feature on Demand ISO from the [Microsoft OEM site](http://go.microsoft.com/fwlink/?LinkId=131359) or the [Device Partner Center](https://devicepartner.microsoft.com/). 
    - For Windows 10, version 1809, LIP .appx files and their associated license files are in the LocalExperiencePack folder on the Language Pack ISO.
    - For previous versions of Windows, Language Interface Packs are available as a separate download.
    - WinRE language packs are distributed on the Language Pack ISO. Don't use the WinPE language packs that ship with the ADK.

-   **IT Professionals** can download language packs from the [Microsoft Next Generation Volume Licensing Site](https://licensing.microsoft.com/).
-   After Windows is installed, users can download and install more languages by selecting **Settings** > **Time & language** > **Language** > **Add a language**. 

Notes: 
* Language components must match the version of Windows. For example, you can't add a Windows 10, version 1809 language pack to Windows 10, version 1803.
* Windows Server: Full language packs are not interchangeable with Windows 10, but some LIPs are. For example, you can add Windows 10, version 1809 LIPs to Windows Server 2019.

## Considerations

* **Install languages, then updates and apps**. If you're adding languages to an image that already contains apps or updates (for example, servicing stack updates (SSU) or cumulative updates (CU), reinstall the apps and updates.

* **Size and performance**
  - You can install multiple languages and components onto the same Windows image. Having too many affects disk space, and can affect performance, especially while updating and servicing Windows.
  - Some languages require more hard-disk space than others.
  - When creating Windows images, you can remove English language components when deploying to non-English regions to save space. You'll need to uninstall them in the reverse order from how you add them.
  - After the Out-Of-Box-Experience (OOBE) is complete, the default language cannot be removed. The default UI language is selected either during the Out-Of-Box-Experience (OOBE), or can be preselected in the image using DISM or an unattended answer file.
  - Some time after OOBE, any preinstalled languages that haven't been used are removed automatically. The language-pack removal task does not remove LIPs.

- **Cross-language upgrades are not supported**. This means that during upgrades or migrations, if you upgrade or migrate an operating system that has multiple language packs installed, you can upgrade or migrate to the system default UI language only. For example, if English is the default language, you can upgrade or migrate only to English.

## Add and remove language packs, LIPs, and features on demand

We'll install the French language, and then add a LIP language (Luxembourgish) that uses French for its base language.

To save space, you can remove English language components when deploying to non-English regions by [uninstalling the language](#remove-a-language-pack-from-a-windows-image) components in the reverse order from how you add them.

### Prepare to modify your images: Installation methods

-   **Offline: Modify an image (install.wim) that you plan to deploy using Windows PE or Windows Setup**:

    Mount the Windows image:

    ```
    md C:\mount\windows
    Dism /Mount-Image /ImageFile:install.wim /Index:1 /MountDir:"C:\mount\windows"
    ```

-   **Online: Modify a running Windows installation** (for example, in [audit mode](boot-windows-to-audit-mode-or-oobe.md))

    You can install languages and LIPs by opening the packages from the Language Pack ISO and Feature on Demand ISO and following the instructions to complete the installation.
    
    You can use the **Settings** > **Time & Language** to modify the settings or download languages from Windows Update. 

    To run these same updates using a script, use the instructions in this topic, replacing `/Image:"C:\mount\windows"` with `/Online`.

    To update the recovery environment, see [Add languages to the recovery environemnt](#add-languages-to-the-recovery-environment).

### Add and remove language packs, LIPs (LXPs), and Features on Demand

Preinstall languages by adding the language packs and their related Features on Demand for all preinstalled languages, including the base languages if you're adding a LIP language.

1.  Mount the Language Pack ISO and the Features on Demand ISO with File Explorer. This will assign them drive letters.

2.  **Add a language pack**:

    ```
    Dism /Image:"C:\mount\windows" /Add-Package /PackagePath="D:\x64\langpacks\Microsoft-Windows-Client-Language-Pack_x64_fr-fr.cab"
    ```

    Where D:\ is the Language Pack ISO.
    
    Verify that it's in the image:

    ```
    Dism /Image:"C:\mount\windows" /Get-Packages
    ```

2.  **Add LIP languages**. In this example, we add Luxembourgish, which requires the fr-FR base language:

    * For Windows 10, version 1809 and later, LIP languages are delivered as LXPs:

      ```
      DISM /Image:"C:\mount\windows" /Add-ProvisionedAppxPackage /PackagePath="D:\LocalExperiencePack\lb-lu\LanguageExperiencePack.lb-LU.Neutral.appx /LicensePath:"D:\LocalExperiencePack\lb-lu\License.xml"
      ```
    
      Where D:\ is the Language Pack ISO

      Verify that it's in the image:

      ```
      DISM /Image:"C:\mount\windows" get-provisionedappxpackages
      ```

    * For earlier versions of Windows 10, LIP languages are delivered as .cab files:

      ```
      Dism /Image:C:\mount\windows /add-package /packagepath:C:\LanguagePack\LIPs\ca-ES\LIP_ca-ES64bit.cab
      ```

3.  **Add [language and region Features on Demand](features-on-demand-language-fod.md)** to support your language packs and LIPs. We recommend including the Basic, Fonts, OCR, Text-to-speech, and Speech recognition FODs if they're available for the languages you’re preinstalling. Additionally, include the handwriting language component FOD if you’re shipping a device with a pen. 

    Not all LIP languages have all language components. Luxembourgish (lb-LU), for example, only has basic and handwriting FODs. You can learn which FODs are available for languages [in the LP to FOD mapping spreadsheet](http://download.microsoft.com/download/C/6/C/C6C91D1F-F96A-40FA-AF9D-E73FA4EAD344/Windows-10-1809-FOD-to-LP-Mapping-Table.xlsx)
    
    Example: adding Basic, OCR, Text-to-Speech, and Speech Recognition to fr-fr:
    ```
    Dism /Image:"C:\mount\windows" /Add-Package /PackagePath:E:\Microsoft-Windows-LanguageFeatures-Basic-fr-fr-Package~31bf3856ad364e35~amd64~~.cab /PackagePath:E:\Microsoft-Windows-LanguageFeatures-OCR-fr-fr-Package~31bf3856ad364e35~amd64~~.cab /PackagePath:E:\Microsoft-Windows-LanguageFeatures-Handwriting-fr-fr-Package~31bf3856ad364e35~amd64~~.cab /PackagePath:E:\Microsoft-Windows-LanguageFeatures-TextToSpeech-fr-fr-Package~31bf3856ad364e35~amd64~~.cab /PackagePath:E:\Microsoft-Windows-LanguageFeatures-Speech-fr-fr-Package~31bf3856ad364e35~amd64~~.cab
    ```
    
    Where E:\ is the Feature on Demand ISO.

    Example: adding Basic and Handwriting to lb-LU:

    ```
    DISM /Image:"C:\mount\windows" /Add-Package /PackagePath:E:\Microsoft-Windows-LanguageFeatures-Basic-lb-lu-Package~31bf3856ad364e35~amd64~~.cab /PackagePath:E:\Microsoft-Windows-LanguageFeatures-Handwriting-lb-lu-Package~31bf3856ad364e35~amd64~~.cab
    ```
        
    Example: adding Thai fonts (requires adding th-TH language pack and Basic first).

    ```
    Dism /Image:"C:\mount\windows" Add-Capability /CapabilityName:Language.Fonts.Thai~~~und-THAI~0.0.1.0 /Source:E:
    Dism /Get-Capabilities /Image:"C:\mount\windows"
    ```

    Verify that they're in the image:
    ```
    Dism /Image:"C:\mount\windows" /Get-Packages
    Dism /Image:"C:\mount\windows" /Get-Capabilities
    ```

5.  **Remove languages, LIPs, LXPs, and Features on Demand**.

    > [!important]
    > You cannot remove a language pack from an offline Windows image if there are pending online actions. The Windows image should be a recently installed and captured image. This will guarantee that the Windows image does not have any pending online actions that require a reboot.

    Get a list of packages and features installed in your image:

    ```
    Dism /Image:"C:\mount\windows" /Get-Packages
    Dism /Image:"C:\mount\windows" /Get-Capabilities
    ```

    Remove languages, .cab-based LIPs, and Features On Demand:

    ```
    Dism /Image:"C:\mount\windows" /Remove-Package /PackageName:<language pack name> /PackageName:<feature on demand name> ...
    ```

    Remove LIPs added through LXPs:

    ```
    Dism /remove-provisionedappxpackage /packagename:Microsoft.LanguageExperiencePack<lang_version>_neutral__8wekyb3d8bbwe
    ```

    Verify that they're no longer in your image:

    ```
    Dism /Image:"C:\mount\windows" /Get-Packages
    Dism /Image:"C:\mount\windows" /Get-Capabilities
    ```

7.  **Change your default language, locale, and other international settings**:

    * For offline images, you can only specify language packs and .cab-based LIPs, not languages delivered as .appx-based LXPs.
    * If you install a LIP by using a .cab file and specify it as the default system UI language, the LIP language will be set as the default UI language (or system locale) and the parent language will be set as the default system UI language (or install language).
    
       ```
       Dism /Image:"C:\mount\windows" /Set-AllIntl:fr-fr
       ```

       See which language settings are available: 

       ```
       Dism /Image:"C:\mount\windows" /Get-Intl
       ```

    * For online images, use Control Panel, or the [International Settings PowerShell cmdlets](https://docs.microsoft.com/powershell/module/internationalcmdlets/?view=winserver2012-ps): `Get-WinSystemLocale` and `Set-WinSystemLocale <language>`. This works with languages delivered as LXPs.

    For more options, see
    - [Default input profiles (input locales)](default-input-locales-for-windows-language-packs.md)
    - [Keyboard identifiers and input method editors (IME)](windows-language-pack-default-values.md)
    - [Time zones](default-time-zones.md) 
    - [DISM Languages and International Servicing Command-Line Options](dism-languages-and-international-servicing-command-line-options.md).

### Add languages to the recovery environment (Windows RE)

We recommend adding languages to [Windows RE](windows-recovery-environment--windows-re--technical-reference.md) for any language you add to Windows.

Not all languages or LIPs have localized recovery images.

Use languages from the Language Pack ISO, not from the Windows 10 ADK, to localize WinRE.

> [!note]
> **Known issue**: Windows RE included with Windows 10 October 2018 Update Thai language image (en-US base language + th-th language pack) shipped with an issue in which an end user will only see UI components (or English) without Thai language text in the Windows Recovery Environment, the text displayed during recovery (Push-button reset), and/or certain screens during the reboot process of feature updates. To fix this issue pre-install the 2018.11D Quality Update.

1.  Mount the recovery image.

    * **Offline**: the recovery image is inside the Windows image:

      ```
      md C:\mount\winre
      Dism /Mount-Image /ImageFile:"C:\mount\windows\Windows\System32\Recovery\winre.wim" /index:1 /MountDir:"C:\mount\winre"
      ```

    * **Online**:

      ```
      md C:\mount\winre
      Dism /Mount-Image /ImageFile:"C:\Windows\System32\Recovery\winre.wim" /index:1 /MountDir:"C:\mount\winre"
      ```
      
      Note, Windows RE is inside the Windows image until the Out of Box Experience, after which it is moved to a separate recovery partition.

2.  Add languages:

    ```
    D:
    cd D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\
    Dism /Image:"C:\mount\winre" /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\lp.cab" 
    Dism /Image:"C:\mount\winre" /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-Rejuv_fr-fr.cab"
    Dism /Image:"C:\mount\winre" /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-EnhancedStorage_fr-fr.cab"
    Dism /Image:"C:\mount\winre" /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-Scripting_fr-fr.cab"
    Dism /Image:"C:\mount\winre" /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-SecureStartup_fr-fr.cab"
    Dism /Image:"C:\mount\winre" /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-SRT_fr-fr.cab"
    Dism /Image:"C:\mount\winre" /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-WDS-Tools_fr-fr.cab"
    Dism /Image:"C:\mount\winre" /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-WMI_fr-fr.cab"
    Dism /Image:"C:\mount\winre" /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-StorageWMI_fr-fr.cab"
    Dism /Image:"C:\mount\winre" /Add-Package /PackagePath:"D:\Windows Preinstallation Environment\x64\WinPE_OCs\fr-fr\WinPE-HTA_fr-fr.cab"
    ```

    Where D:\ is the Language Pack ISO.

3.  Verify that they're in the image:

    ```
    Dism /Get-Packages /Image:"C:\mount\winre"
    ```

    Example output from /Get-Packages: 

    ```
    Package Identity : Microsoft-Windows-WinPE-Rejuv_fr-fr ... fr-FR~10.0.9926.0 State : Installed
    ```

4.  Commit changes to the recovery image:

    ```
    Dism /Commit-Image /MountDir:"C:\mount\winre"
    ```

    For online images, also remove the mount folder:
    
    ```
    rmdir /s "C:\mount\winre"
    ```

### Capture the changes

*  **Offline: For Windows images (install.wim)**

   Commit changes to the Windows image:

   ```
   Dism /Commit-Image /MountDir:"C:\mount\windows"
   ```

*  **Online: Modify a running Windows installation**

   Generalize and capture the image:
   ```
   %WINDIR%\system32\sysprep\sysprep.exe /generalize /shutdown /oobe
   ``` 
   
   To learn more, see [generalize](sysprep--generalize--a-windows-installation.md).

## Next steps:

**Localize more of Windows:**

* [Out of Box Experience (OOBE)](how-oobexml-works.md): Create localized end user license agreements (EULA), registration pages, and instructions for pairing keyboards and mice.
* [Retail demo experience](https://docs.microsoft.com/windows-hardware/customize/desktop/retail-demo-experience#add-retail-demo-mode-including-language-packs-to-your-images): Showcase your new devices on the retail sales floor with localized content.

**Localize the installation process**

* [Add languages to Windows Setup](add-multilingual-support-to-windows-setup.md): Now that you've added languages to your Windows image, make sure they appear in Windows Setup. You can also create Windows installation media that works in the user's preferred language.

* [Add languages to WinPE](winpe-mount-and-customize.md) to help your technicians install Windows in their preferred language.

* [Add languages to a Windows distribution share](add-multilingual-support-to-a-windows-distribution.md) to help users on a corporate network select Windows in their preferred language

## <span id="related_topics"></span>Related topics

* [Features On Demand](features-on-demand-v2--capabilities.md)
* Add languages to [Windows Recovery Environment (WinRE)](customize-windows-re.md)




## <span id="related_topics"></span>Related topics

[Localize Windows](localize-windows.md)

[Service a Windows Image Using DISM](service-a-windows-image-using-dism.md)

[DISM - Deployment Image Servicing and Management Technical Reference for Windows](dism---deployment-image-servicing-and-management-technical-reference-for-windows.md)

[DISM Languages and International Servicing Command-Line Options](dism-languages-and-international-servicing-command-line-options.md)

[DISM Unattended Servicing Command-Line Options](dism-unattended-servicing-command-line-options.md)

[Windows System Image Manager Technical Reference](https://docs.microsoft.com/windows-hardware/customize/desktop/wsim/windows-system-image-manager-technical-reference)
