---

Description: Add Multilingual Support to a Windows Distribution
ms.assetid: 2da53fc7-4c4d-4cea-9a98-0db4eacd33d2
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Add Multilingual Support to a Windows Distribution

ms.date: 05/02/2017
ms.topic: article

redirect_url: https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/add-multilingual-support-to-a-windows-distribution

---

# Add Multilingual Support to a Windows Distribution


You can use Windows Setup to deploy a multilingual edition of Windows. This is a typical scenario for corporations that deploy Windows in a multilingual environment where the users must be able to switch the display language between multiple languages on a single computer. This procedure requires the following steps:

1.  Copy one or more language packs to the **\\Langpacks** directory in the *Windows distribution*. The Windows distribution is the contents of the Windows retail DVD.
2.  Update the Lang.ini file.
3.  Use Setup to install the language packs that are in the distribution share.

**Important**  
Adding language packs to the **\\Langpacks** directory can extend the Windows Setup installation time. Packages in the **\\Langpacks** directory are added to the Windows image during the **windowsPE** configuration pass, before Windows is actually installed. If Windows Setup must install several language packs, then installation might be delayed.

 

**To add language packs to a Windows Distribution**

1.  Copy the Windows distribution to a local directory. For example, copy the contents of the Windows product DVD to a directory named **C:\\my\_distribution**.

2.  Locate the language pack .cab files for the languages that you want to add to the Windows distribution and copy them to a local directory. 

3.  Create the **\\Langpacks** directory in the distribution share. For example:

    ```
    mkdir C:\my_distribution\langpacks 
    ```

4. Create folders in the **\\Langpacks** folder for each language pack you're adding

    ```
    mkdir C:\my_distribution\Langpacks\fr-fr
    ```

5.  Copy the language packs to the language-specific folders you created in **\\Langpacks**. For example:

    ```
    xcopy C:\LPs\Microsoft-Windows-Client-Language-Pack_x64_fr-fr.cab C:\my_distribution\Langpacks\fr-fr\Microsoft-Windows-Client-Language-Pack_x64_fr-fr.cab
    ```

6. Rename the language pack in each folder to `lp.cab`.

    ```
    ren C:\my_distribution\Langpacks\fr-fr\Microsoft-Windows-Client-Language-Pack_x64_fr-fr.cab lp.cab
    ```

6.  (Optional) To make additional languages available in Windows Setup, copy the localized Windows Setup sources to the distribution share. For example:

    ```
    xcopy E:\sources\fr-fr C:\my_distribution\sources\fr-fr /cherkyi 
    xcopy E:\sources\de-de C:\my_distribution\sources\de-de /cherkyi
    ```

    Where *E:* is the location of the Windows distribution that contains the localized Windows Setup resources.

    The **/cherkyi** parameters for the **xcopy** command copies all hidden files and subdirectories and overwrites all files in the target directory.

6.  Mount the Windows image that is in the distribution share. This step is required for the Deployment Image Servicing and Management tool (DISM.exe) to report the list of languages that are installed in the .wim file, and to recreate the Lang.ini file. Use DISM to mount the Windows image. For example:

    ```
    DISM.exe /Mount-Image /ImageFile:C:\my_distribution\sources\install.wim /index:1 /MountDir:C:\mount\windows
    ```

7.  Report the languages that are available in the distribution share or installed to the Windows image by using the **/Get-Intl** option and specifying the distribution share. For example:

    ```
    DISM.exe /image:c:\mount\windows /distribution:c:\my_distribution /Get-Intl
    ```

    Verify that the correct languages are displayed as available languages and that **The other available languages in the distribution** display the correct languages. For example:

    ```
    Default system UI language : en-US
    System locale : en-US
    Default time zone : Pacific Standard Time
    User locale for default user : en-US
    Location : United States (GEOID = 244)
    Active keyboard(s) : 0409:00000409
    Keyboard layered driver : PC/AT Enhanced Keyboard (101/102-Key)

    Installed language(s): en-US
    Type : Fully localized language.

    Reporting distribution languages.

    The default language in the distribution is:
    en-US

    The other available languages in the distribution are:
    es-es, fr-fr
    ```

8.  Recreate the Lang.ini file. For example:

    ```
    DISM.exe /image:c:\mount\windows /Gen-LangINI /distribution:c:\my_distribution
    ```

    When you add or remove language packs from a Windows distribution, you must recreate the Lang.ini file. The Lang.ini file is located in the sources directory of the Windows distribution and is used during Windows Setup. The lang.ini file in the sources directory should look similar to the following:

    ```
    [Available UI Languages]
    en-US = 3
    de-de = 0
    fr-fr = 0

    [Fallback Languages]
    en-US = en-us
    ```

    > [!Note]
    >You can choose a language for Windows Setup from those that are available in the distribution share when you run Setup from a full operating system only. If you run Windows Setup for bootable media or Windows PE, you must add optional components to the Boot.wim file for multilingual support. For more information, see [Add languages to Windows Setup](add-multilingual-support-to-windows-setup.md).

     

9.  Unmount the .wim file and commit the changes. For example:

    ```
    DISM.exe /Unmount-Image /MountDir:C:\mount\windows /commit 
    ```

    You can now run Windows Setup. During the installation, you will be prompted to choose one of the languages you added to the distribution share.

## <span id="related_topics"></span>Related topics


[DISM Languages and International Servicing Command-Line Options](dism-languages-and-international-servicing-command-line-options.md)

[Configure International Settings in Windows](configure-international-settings-in-windows.md)

 

 






