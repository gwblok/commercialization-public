---

Description: Add languages to Windows Setup
ms.assetid: 242b963c-79fc-450b-90d7-c736965797b7
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Add Multilingual Support to Windows Setup

ms.date: 11/06/2018
ms.topic: article

---

# Add languages to Windows Setup

To support multiple languages with Windows Setup:

* Add languages to the Windows Setup image (boot.wim index:2) to help technicians or users install Windows images through Windows Setup.
* When you add languages to a Windows image (install.wim), add a list of languages (lang.ini) so that during installation, the technician or user can select which language is installed as the default language.

You can include a different set of languages for your Windows images and Windows Setup.

## Prerequisites

- A technician computer that has the Windows Assessment and Deployment Kit (Windows ADK) installed with the **Deployment tools** option, including the **WinPE add-on**.

**CopyPE** and **MakeWinPEMedia** are installed when you choose the **Deployment tools** and **Windows Preinstallation Environment** options when [installing the ADK](https://docs.microsoft.com/en-us/windows-hardware/get-started/adk-install). If you're using the ADK for Windows 10, version 1809, Windows PE is a separate add-on that you download and install after you install the ADK. You can [download the WinPE add-on from the Download Center](https://go.microsoft.com/fwlink/?linkid=2022233).

- Windows installation media for all languages that you are creating media.

- The Windows language pack ISO.

## Step 1. Copy installation files to a working folder

On your technician PC, copy the Windows installation files from the Windows installation media to a local directory. 

If you are creating media for use with a customized image, you must use the Windows media that corresponds to the version of your customized image. For example, if you are building a custom Windows 10 Setup image, you must use the original Windows 10 product media.

```
md C:\my_distribution
xcopy /E D: C:\my_distribution
```

Where *D:* is the location of the Windows installation media.

## Step 2. Add languages to the default Windows Setup boot image (index:2)

1.  Click **Start**, and type **deployment**. Right-click **Deployment and Imaging Tools Environment** and then select **Run as administrator**.

2.  Mount the second image (index 2) in Boot.wim.

    ```
    md C:\mount\boot 
    Dism /mount-image /imagefile:C:\my_distribution\sources\boot.wim /index:2 /mountdir:C:\Mount\boot
    ```

3.  Add language packs from the Windows ADK into your mounted image using **Dism /Add-Package** for each language you want to support. Add *lp.cab*, *WinPE-setup_\<language>.cab*. For Windows 10, also add *WinPE-Setup-client_\<language>.cab*. For Windows Server, also add *WinPE-Setup-server_\<language>.cab*

    Windows PE language packs are available in the Windows ADK.

    **For Windows 10:**

    ```
    Dism /image:C:\mount\boot /add-package /packagepath:"C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\fr-fr\lp.cab"

    Dism /image:C:\mount\boot /add-package /packagepath:"C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\fr-fr\WinPE-Setup_fr-fr.cab"

    Dism /image:C:\mount\boot /add-package /packagepath:"C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\fr-fr\WinPE-Setup-Client_fr-fr.cab"
    ```

    **For Windows Server:**  

    ```
    Dism /image:C:\mount\boot /add-package /packagepath:"C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\fr-fr\lp.cab"

    Dism /image:C:\mount\boot /add-package /packagepath:"C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\fr-fr\WinPE-Setup_fr-fr.cab"

    Dism /image:C:\mount\boot /add-package /packagepath:"C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\fr-fr\WinPE-Setup-Server_fr-fr.cab"
    ```

     
4.  For Japanese (ja-JP), Korean (ko-KR), and Chinese (zh-HK, zh-CN, zh-TW), add font support to your image. For example, to add Japanese font support:

    ```
    Dism /image:C:\mount\boot /add-package /packagepath:"C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Preinstallation Environment\amd64\WinPE_OCs\WinPE-FontSupport-JA-JP.cab"
    ```

5.  Change the Windows Setup default language:

    ```
    Dism /image:C:\mount\boot /Set-SetupUILang:fr-FR /distribution:C:\my_distribution
    ```

    For more information about specifying different international settings, see [DISM Languages and International Servicing Command-Line Options](dism-languages-and-international-servicing-command-line-options.md).


## Step 3: Add localized Windows Setup resources to the Windows distribution

In this step you copy the language-specific Setup resources from each language-specific Windows distribution to the Sources folder in your Windows distribution. For example, mount the fr-FR Windows installation media as drive E: and copy the Fr-FR sources folder to your Windows distribution. 

Note, language interface packs (LIP) are not supported on Windows Setup.

-   Copy the localized Windows Setup files to your Windows distribution.

    ```
    xcopy E:\sources\fr-fr C:\my_distribution\sources\fr-fr /cherkyi 
    ```

    Where *E:* is the location of the Windows installation media that contains the localized Windows Setup resources.

## Step 4. Add language packs to the Windows image 

To modify the languages in the Windows image, see [Add Language Packs to Windows](add-language-packs-to-windows.md).

After you do this, update the list of available Windows languages (Lang.ini):

1.  Recreate the Lang.ini file to reflect the additional languages.

    ```
    Dism /image:C:\mount\windows /gen-langINI /distribution:C:\my_distribution
    ```

3.  Copy the lang.ini file in the Windows distribution to the boot folder.

    ```
    Xcopy C:\my_distribution\sources\lang.ini C:\mount\boot\sources\lang.ini
    ```

## Step 6: Commit the changes to the Windows images

    ```
    Dism /unmount-image /mountdir:C:\mount\boot /commit 
    Dism /unmount-image /mountdir:C:\mount\windows /commit
    ```

## Step 7: Create the media

### USB flash drive

Use **MakeWinPEMedia** with the `/UFD` option to format and install Windows PE to the USB flash drive, specifying the USB key's drive letter:

    ```
    MakeWinPEMedia /UFD C:\my_distribution F:
    ```

To learn more, see [WinPE: Create USB Bootable drive](winpe-create-usb-bootable-drive.md).

### DVD or CD

1. Create a [boot order file](oscdimg-command-line-options.md). This is required for DVD or CD images larger than 4.5 GB to make sure that boot files are located at the beginning of the image.

   For example, copy this into a text file called C:\Temp\BootOrder.txt: 

   ```
   boot\bcd
   boot\boot.sdi
   boot\bootfix.bin
   boot\bootsect.exe
   boot\etfsboot.com
   boot\memtest.efi
   boot\memtest.exe
   boot\en-us\bootsect.exe.mui
   boot\fonts\chs_boot.ttf
   boot\fonts\cht_boot.ttf
   boot\fonts\jpn_boot.ttf
   boot\fonts\kor_boot.ttf
   boot\fonts\wgl4_boot.ttf
   sources\boot.wim
   ```

2. Create the ISO file, using the boot order file:

   ```
   Oscdimg -m -n -yo C:\temp\BootOrder.txt -bC:\winpe_amd64\Efisys.bin C:\winpe_amd64\winpeamd64.iso
   ```

3. Right-click the ISO file and select **Burn disc image**.

## Related topics

[Windows Setup Technical Reference](windows-setup-technical-reference.md)

[DISM Image Management Command-Line Options](dism-image-management-command-line-options-s14.md)

[DISM Windows PE Servicing Command-Line Options](dism-windows-pe-servicing-command-line-options.md)

[Oscdimg Command-Line Options](oscdimg-command-line-options.md)

[WinPE: Mount and Customize](winpe-mount-and-customize.md)

[WinPE: Install on a Hard Drive (Flat Boot or Non-RAM)](winpe-install-on-a-hard-drive--flat-boot-or-non-ram.md)

 

 






