---

Description: 'Lab 8: Add branding and license agreements'
ms.assetid: a29101dc-4922-44ee-a758-d555e6cf39fa
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Lab 8: Add branding and license agreements'

ms.date: 05/02/2017
ms.topic: article


redirect_url: https://docs.microsoft.com/windows-hardware/manufacture/desktop/how-oobexml-works
---

# Lab 8: Add branding and license agreements

You can add your own branding and license terms to Windows. 

For multi-region or multi-language images, you can create region specific license terms. These display to the user during the first login experience, based on the region or language that they choose. 

Note: If the license terms are included, the OEM must include a version of the license terms in each language that is preinstalled onto the PC. You can read more about creating license terms at [OEM license terms](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/oem-license).

Use the examples in the [USB-B.zip](http://download.microsoft.com/download/3/F/2/3F2646EF-D589-498C-9F07-DE5549BE018E/USB-B.zip) key.

## <span id="Mount_the_image"></span>Mount the image

Use the steps from [Lab 3: Add device drivers (.inf-style)](add-device-drivers.md) to mount the image. The short version:

1.  Open the command line as an administrator (**Start** > type **deployment** > right-click **Deployment and Imaging Tools Environment** > **Run as administrator**.)

2.  Make a backup of the file (`copy "D:\Images\Win10_x64\sources\install.wim" D:\Images\install-backup.wim`)

3.  Mount the image (`md C:\mount\windows`, then `Dism /Mount-Image /ImageFile:"D:\Images\install.wim" /Index:1 /MountDir:"C:\mount\windows" /Optimize`)


## <span id="Create_license_files"></span>Create license files

1.  Create folders under a working folder, for example:

    `C:\mount\windows\Windows\System32\oobe\info\default\` 

2.  Add subfolders for each language using the **[Language Decimal Identifier](available-language-packs-for-windows.md)** corresponding the language. Do this step for each language pack added to the Windows image.

    For example, if en-us and de-de language packs are added to the Windows image, add a folder named “1033” (representing en-us language) under C:\mount\windows\Windows\System32\oobe\info\default\. Then add a folder named “1031” (representing de-de language) under the same directory.

    ```
    md c:\mount\windows\windows\system32\oobe\info\default\1033
    md c:\mount\windows\windows\system32\oobe\info\default\1031
    ```

3.  Create license terms documents using the .rtf file format for each language specified. Move each license term document to the corresponding language folder. For example:

    ```
    C:\mount\windows\Windows\System32\oobe\info\default\1033\agreement.rtf  (English version)
    C:\mount\windows\Windows\System32\oobe\info\default\1031\agreement.rtf  (German version)
    ```
    
    Agreement.rtf EULA samples are in D:\USB-B\resources\
    
4. Open a text editor and create .html versions of your license terms. Save the terms to the same folders as the .rtf versions. You can use the [EULA example](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/oem-license#eula-example) from [OEM license terms](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/oem-license) to create sample files.  The names of the EULA files should be identical, except for the extension.

    ```
    C:\mount\windows\Windows\System32\oobe\info\default\1033\agreement.html  (English version)
    C:\mount\windows\Windows\System32\oobe\info\default\1031\agreement.html  (German version)
    ```


5.  Create an **oobe.xml** file to specify the agreement.rtf file path. Windows will automatically look for the associated agreement.html file.

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <FirstExperience>
      <oobe>
        <oem>
	      <eulafilename>agreement.rtf</eulafilename>
        </oem>
      </oobe>
    </FirstExperience>
    ```

6.  Copy your **oobe.xml** to each language folder.

    ```
    Copy D:\configset\oobe.xml c:\mount\windows\windows\system32\oobe\info\default\1033
    Copy D:\configset\oobe.xml c:\mount\windows\windows\system32\oobe\info\default\1031
    ```

7.  For Chinese Hong Kong, add the following OOBE.xml file. (In Windows 10 version 1607, the Chinese Hong Kong language pack was merged into the Chinese Taiwan language pack, so for this region, these steps are now required).

    File: c:\mount\windows\Windows\System32\OOBE\Info\OOBE.xml
    
    ```
    <?xml version="1.0" encoding="utf-8" ?>
    <FirstExperience>
      <oobe>
        <defaults>
          <location>104</location>
        </defaults>
      </oobe>
    </FirstExperience>
    ```

8.  Verify that each language folder contains an **oobe.xml** file, an **agreement.rtf** file, and an **agreement.html** file in that corresponding language.


### <span id="Create_image_files"></span>Create image info file
1.  Create an **csup.txt** file to specify when the Windows image was created. This file must include the date that the image was created, in the form of 'MM-DD-YYYY', with no other characters, on a single line at the top of the file.

    ```
    10-05-2017
    ```
2.  Copy the image info file into the image.

    ```
    xcopy C:\temp\CSUP.txt c:\mount\windows\windows\csup.txt
    ```

### <span id="Add_custom_logo_and_wallpapaer"></span>Add a custom logo and wallpaper

Learn how to apply the logo using the [User Experience Windows Engineering Guide (UX WEG)](https://myoem.microsoft.com/oem/myoem/en/topics/Licensing/roylicres/ost2016/Pages/DP-UXWEGWin10.aspx) and for logo resolution requirements. 

1.  Copy the logo files into the image into the \\Windows\\System32\\OEM\\ folder. Create the folder if it doesn’t exist.

    ```
    MkDir c:\mount\windows\windows\system32\OEM
    Copy D:\OEM c:\mount\windows\windows\system32\OEM
    ```

## <span id="Unmount_the_images"></span> Unmount the images

1.  Close all applications that might access files from the image.

2.  Commit the changes and unmount the Windows image:

    ```
    Dism /Unmount-Image /MountDir:"C:\mount\windows" /Commit
    ```

    where *C* is the drive letter of the drive that contains the image.

    This process may take several minutes.

## <span id="Try_it_out"></span>Try it out

**Apply the image to a new PC**
Use the steps from [Lab 2: Deploy Windows using a script](deploy-windows-with-a-script-sxs.md) to copy the image to the storage USB drive, apply the Windows image and the recovery image, and boot it up. The short version:

1.  Copy the image file to the storage drive.
2.  [Boot the reference device to Windows PE using the Windows PE USB key](install-windows-pe-sxs.md).
3.  Find the drive letter of the storage drive (`diskpart, list volume, exit`).
4.  Apply the image: `D:\Deployment\ApplyImage.bat D:\Images\install.wim`.
5.  Disconnect the drives, then reboot (`exit`).
	
**Verify license terms**

Log into the system as if you were a new user. Select your language or region of required. The correct license terms should show up during this first login experience.

> [!div class="nextstepaction"]
> [Lab 9: Make changes from Windows (audit mode)](prepare-a-snapshot-of-the-pc-generalize-and-capture-windows-images-blue-sxs.md)