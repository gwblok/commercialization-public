---

Description: Add and Remove Drivers to an Offline Windows Image
ms.assetid: 71651630-2e26-4174-8161-8f83b8ae4bc3
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Add and Remove Drivers to an Offline Windows Image

ms.date: 04/16/2018
ms.topic: article
ms.custom: RS5
---

# Add and Remove Drivers to an offline Windows Image


You can use DISM to install or remove driver (.inf) files in an offline Windows or WinPE image. You can either add or remove the drivers directly by using the command prompt, or apply an unattended answer file to a mounted .wim, .ffu, .vhd, or .vhdx file.

When you use DISM to install a device driver to an offline image, the device driver is added to the driver store in the offline image. When the image is booted, Plug and Play (PnP) runs and associates the drivers in the store to the corresponding devices on the computer.

>[!Note]
>To add drivers to a Windows 10 image offline, you must use a technician computer running Windows 10, Windows Server 2016, or Windows Preinstallation Environment (WinPE) for Windows 10. Driver signature verification may fail when you add a driver to a Windows 10 image offline from a technician computer running any other operating system.

To learn how to add a driver on a running Windows PC, see [Add a driver online in audit mode](add-a-driver-online-in-audit-mode.md) or [Install a plug and play device](http://go.microsoft.com/fwlink/?LinkId=139151). To learn how to add a driver to a PC running WinPE, see [Drvload command line options](drvload-command-line-options.md).

## Driver types

-  **.inf-style drivers**: Many drivers include an information file (with an .inf extension) to help install the driver. These can be installed using tools described in this topic.    
-  **.exe-style drivers**: Drivers without an .inf file often must be installed like typical Windows desktop applications. To learn how to add these, see [Add a driver online in Audit Mode](add-a-driver-online-in-audit-mode.md)
-  **Boot-critical drivers**: Graphics and storage drivers may sometimes need to be added to the Windows image (as shown in this topic), as well as the Windows PE image, and in the Windows recovery (WinRE) image. 

## Add drivers to an offline Windows image

To add drivers to an offline image, you have to mount an image prior to adding drivers. 

If you're adding drivers to a WinPE image, you can add them to the WinPE image in the output folder you specified when you [ran copype](winpe-create-usb-bootable-drive.md#step-1-create-working-files), for example: `C:\WinPE_amd64\media\sources\boot.wim`. This ensures that drivers will be included in WinPE each time you build WinPE media from that folder.

1.  Mount a Windows image. For example:

    ```
    Dism /Mount-Image /ImageFile:C:\test\images\install.wim /MountDir:C:\test\offline
    ```
    See [Mount and modify a Windows image using DISM](mount-and-modify-a-windows-image-using-dism.md) for more info.

2.  Add a driver to the image.

    ```
    Dism /Image:C:\test\offline /Add-Driver /Driver:C:\drivers\mydriver.inf
    ```

    To install all of the drivers from a folder and all its subfolders, point to the folder and use the **/Recurse** option.

    ```
    Dism /Image:C:\test\offline /Add-Driver /Driver:c:\drivers /Recurse
    ```

    To see all DISM driver servicing command line options, see [DISM driver servicing command-line options](dism-driver-servicing-command-line-options-s14.md).

>[!Warning]
>Using `/Recurse` can be handy, but it's easy to bloat your image with it. Some driver packages include multiple .inf driver packages, which often share payload files from the same folder. During installation, each .inf driver package is expanded into a separate folder. Each individual folder has a copy of the payload files. We've seen cases where a popular driver in a 900MB folder added 10GB to images when added with the /Recurse option.

    To install an unsigned driver, use **/ForceUnsigned** to override the requirement that drivers installed on X64-based computers must have a digital signature.

    ```
    Dism /Image:C:\test\offline /Add-Driver /Driver:C:\drivers\mydriver.inf /ForceUnsigned
    ```

3.  Check to see if the driver was added. Drivers added to the Windows image are named Oem\*.inf. This guarantees unique naming for newly added drivers. For example, the files MyDriver1.inf and MyDriver2.inf are renamed Oem0.inf and Oem1.inf.

    ```
    Dism /Image:C:\test\offline /Get-Drivers 
    ```

5.  Commit the changes and unmount the image.

    ```
    Dism /Unmount-Image /MountDir:C:\test\offline /Commit
    ```

## Remove drivers from an offline Windows image

1.  At an elevated command prompt, mount the offline Windows image:

    ```
    Dism /Mount-Image /ImageFile:C:\test\images\install.wim /Name:"Windows 10 Home" /MountDir:C:\test\offline
    ```

2.  Remove a specific driver from the image. Multiple drivers can also be removed on one command line.

    ```
    Dism /Image:C:\test\offline /Remove-Driver /Driver:OEM1.inf /Driver:OEM2.inf
    ```

>[!Warning]
>Removing a boot-critical driver package can make the offline Windows image unbootable. For more information, see [DISM Driver Servicing Command-Line Options](dism-driver-servicing-command-line-options-s14.md).
     

3.  Commit the changes and unmount the image.

    ```
    Dism /Unmount-Image /MountDir:C:\test\offline /Commit
    ```

## Add drivers to an offline Windows image by using an unattended answer file

1.  Gather the device driver .inf files that you intend to install on the Windows image.

>[!Note]
>All drivers in the directory and subdirectories that are referenced in the answer file are added to the image. You should manage the answer file and these directories carefully to address concerns about increasing the size of the image with unnecessary driver packages.

2.  Use Windows System Image Manager (Windows SIM) to create an answer file that contains the paths to the device drivers that you want to install.

    - Add the `Microsoft-Windows-PnpCustomizationsNonWinPE\DriverPaths\PathAndCredentials\Credentials` component to your answer file in the **offlineServicing** configuration pass.
    
    For each location that you intend to access, add a separate **PathAndCredentials** list item by right-clicking on **DriverPaths** in the _Answer File_ pane and clicking **Insert New PathAndCredentials**.

    See [Configure components and settings in an answer file](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file) for information on how to modify an answer file.

3.  For each path in `Microsoft-Windows-PnpCustomizationsNonWinPE`, specify the path to the device driver and the credentials that are used to access the file, if the file is on a network share.

>[!Note]
>When you include multiple device driver paths by adding multiple **PathAndCredentials** list items, you must increment the value of **Key** for each path. For example, you can add two separate driver paths where the value of **Key** for the first path is equal to **1** and the value of **Key** for the second path is equal to **2**.

4.  Save the answer file and exit Windows SIM. The answer file must resemble the following sample.

    ```
    <?xml version="1.0" ?><unattend xmlns="urn:schemas-microsoft-com:asm.v3" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State">
       <settings pass="offlineServicing">
          <component name="Microsoft-Windows-PnpCustomizationsNonWinPE" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS">
             <DriverPaths>
                <PathAndCredentials wcm:keyValue="1">
                   <Path>\\networkshare\share\drivers</Path>
                   <Credentials>
                      <Domain>Fabrikam</Domain>
                      <Username>MyUserName</Username>
                      <Password>MyPassword</Password>
                   </Credentials>
                </PathAndCredentials>
             </DriverPaths>
          </component>
       </settings>
    </unattend>
    ```

5.  Mount the Windows image that you intend to install the drivers to by using DISM:

    ```
    Dism /Mount-Image /ImageFile:C:\test\images\install.wim /Index:1 /MountDir:C:\test\offline
    ```

    If you're working with a VHD or FFU, specify `/Index:1`.

6.  Apply the answer file to the mounted Windows image:

    ```
    DISM /Image:C:\test\offline /Apply-Unattend:C:\test\answerfiles\myunattend.xml
    ```

    For more information about how to apply an answer file, see [DISM Unattended Servicing Command-Line Options](dism-unattended-servicing-command-line-options.md).

    The .inf files referenced in the path in the answer file are added to the Windows image.

7. Check to see if the driver was added. Drivers added to the Windows image are named Oem\*.inf. This guarantees unique naming for newly added drivers. For example, the files MyDriver1.inf and MyDriver2.inf are renamed Oem0.inf and Oem1.inf.

    For example, type:

    ```
    Dism /Image:C:\test\offline /Get-Drivers 
    ```

8. Unmount the .wim file and commit the changes. For example, type:

    ```
    Dism /Unmount-Image /MountDir:C:\test\offline /Commit
    ```

If you need drivers for WinPE to see the local hard disk drive or a network, you must use the **windowsPE** configuration pass of an answer file to add drivers to the WinPE driver store and to reflect boot-critical drivers required by WinPE. For more information, see [Add Device Drivers to Windows During Windows Setup](add-device-drivers-to-windows-during-windows-setup.md).

## <span id="related_topics"></span>Related topics


[Device Drivers and Deployment Overview](device-drivers-and-deployment-overview.md)

[Add Device Drivers to Windows During Windows Setup](add-device-drivers-to-windows-during-windows-setup.md)

[DISM - Deployment Image Servicing and Management Technical Reference for Windows](dism---deployment-image-servicing-and-management-technical-reference-for-windows.md)

 





