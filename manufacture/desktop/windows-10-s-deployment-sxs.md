---

Description: 'How to create a Windows 10 S image'
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Windows 10 in S mode deployment lab'

ms.date: 04/20/2018
ms.topic: article


---

# Windows 10 in S mode deployment lab

Starting with Windows 10 in S mode, creating a deployment of Windows 10 in S mode starts with a regular base Windows 10 image. S mode is applied by applying an unattend file to a mounted Windows image. When working with a PC that is in S mode, the manufacturing process has some differences when compared to other versions of Windows. When [planning your deployment](windows-10-s-planning.md), you have to make sure that your [drivers](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/Windows10SDriverRequirements) and [apps](https://docs.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-test-windows-s) are supported by Windows 10 in S mode.

This lab walks you through the process of configuring a Windows 10 image in S mode for deployment. We'll customize an image, set S mode with unattend, add the manufacturing registry key in WinPE, and then remove the registry key in Audit Mode. Then we'll configure recovery and prepare the image for shipment.

> [!Note]
> If you're building a Windows 10 S image, we'll call out the differences between Windows 10 in S mode and Windows 10 S.

Let's get started.

## Get the tools you need

To start building an image for deployment, here's what you'll need:

- Windows 10 image
    - For Windows 10 in S mode, use a Windows Home or Windows Professional image
        **or**
    - For Windows 10 S, use a Windows 10 S image
- Technician PC running Windows 10, Version 1803 or later
- Reference PC where you can deploy your image
- The [latest version of the ADK](https://developer.microsoft.com/en-us/windows/hardware/windows-assessment-deployment-kit) installed on your technician PC
- A USB key that you can format
- [Deployment scripts](http://go.microsoft.com/fwlink/p/?LinkId=800657)
- Customizations such as drivers or language packs
- The latest General Distribution Release update from [the Microsoft Update Catalog](http://www.catalog.update.microsoft.com)

## Format your USB key

To prepare your USB drive, you'll create separate FAT32 and NTFS partitions. The following creates two partitions on a USB drive; one 2GB FAT32 partition, and one NTFS partition that uses the rest of the available space on the drive. You want to make sure that your USB drive has enough free space for the 2GB WinPE partiton and to hold large images on the NTFS partition:

1.  On your technician PC, start the **Deployment and Imaging Tools Environment**  as an administrator:
    -  Click **Start**, type **Deployment and Imaging Tools Environment**. Right-click **Deployment and Imaging Tools Environment** and select **Run as administrator**.

2. Open diskpart.

    ```
    diskpart
    ```

3. Select your your USB key's disk number, and run the `clean` command. This command will make any data on your USB key inaccessible. Make sure you've backed up any data that you want to keep.

    ```
    list disk
    select <disk number>
    clean
    ```
    Where \<disk number> is the number of your USB drive

4. Create the FAT32 partiton for WinPE, label it "Windows PE" and mark it active.

    ```
    create partition primary size=2000
    format quick fs=fat32 label="Windows PE"
    assign letter=P
    active
    ```
5. Create the NTFS partition where you'll store your images and customizations.
    
    ```
    create partition primary
    format fs=ntfs quick label="Data"
    assign letter=T
    list vol
    exit
    ```


## Make a bootable WinPE partition on your USB key

On your technician PC:

1.  Open the Deployment and Imaging Tools Environment as administrator.

2.  Copy the base WinPE files into a new folder:

    ``` 
    copype amd64 C:\winpe_amd64
    ```

3. Copy the WinPE files to your FAT32 partition.

    ```
    MakeWinPEMedia /UFD C:\winpe_amd64 P:
    ```
    When prompted, press **Y** to format the drive and install WinPE.

For more information about how to create a WinPE drive, see [WinPE: Create USB bootable drive](winpe-create-usb-bootable-drive.md).

## Create Data USB partition

1. In File Explorer, open the deployment scripts zip and copy the scripts folder to the Data partition of your USB drive. 
2. From the Deployment and Imaging Tools Environment use copydandi.cmd to copy deployment and imaging tools to your USB drive

    ```
    copydandi amd64 T:\deploymenttools
    ```
    
3. Copy any other customizations you need for Audit mode.

## Mount install.wim and winre.wim

Mounting a Windows image is the same process that we used to mount the WinPE image earlier. When you mount your Windows image (install.wim), you'll be able to access a second image, WinRe.wim, which is the image that supports recovery scenarios. Updating install.wim and WinRE.wim at the same time helps you keep the two images in sync, which ensures that recovery goes as expected.

1.	Mount the Windows 10 iso in File Explorer.

2.	Create a temporary folder (c:\temp) and then copy install.wim from D:\Sources (Where D: is the drive letter of the mounted image) to the temporary folder.

    ```
    md c:\temp
    copy d:\sources\install.wim c:\temp
    ```

3.	Open the Deployment and Imaging Tools Environment as an administrator.

4.	Create a folder for mounting images, and then mount install.wim. 

    ```
    Md C:\mount\windows
    Dism /Mount-Wim /WimFile:C:\temp\install.wim /index:1 /MountDir:C:\mount\windows
    ```

5.	Create a mount folder for the Windows RE Image file from your mounted image, and then mount the WinRE image.

    ```
    Md c:\mount\winre 
    Dism /Mount-Wim /WimFile:C:\mount\windows\Windows\System32\Recovery\winre.wim /index:1 /MountDir:C:\mount\winre
    ```

    **Troubleshoot:** If winre.wim cannot be seen under the specified directory, use the following command to set the file visible:

    ```
    attrib -h -a -s C:\mount\windows\Windows\System32\Recovery\winre.wim
    ```

    **Troubleshoot:** If mounting operation fails, make sure the Windows 10 version of DISM is the one installed with the Windows ADK is being used and not an older version that might be on the Technician Computer. Don't mount images to protected folders, such as the User\Documents folder.  If DISM processes are interrupted, consider temporarily disconnecting from the network and disabling virus protection.

For more information about mounting a Windows image, see [Mount and Modify a Windows Image Using DISM](mount-and-modify-a-windows-image-using-dism.md).

To learn about customizing WinRE, see [Customize Windows RE](customize-windows-re.md).

## Enable customizations

### Enable S mode

> **Note:** This section doesn't apply if you're starting with Windows 10 S media. If this doesn't apply, [skip to the next section](#add-the-manufacturing-registry-key).

Before customizing an image, use the offline servicing pass of unattend to set a Windows PC to S mode. 

1. Use Windows SIM to create an unattend file.
2. Add `SkuPolicyRequired` to the offlineServicing pass
3. Set `SkuPolicyRequired` to `1`
4. Save the file as unattend.xml
5. Copy unattend.xml to the mounted Windows image:
    
    ```
    MkDir c:\mount\windows\Windows\Panther
    Copy unattend.xml  C:\mount\windows\Windows\Panther\unattend.xml
    ```

6. Apply the unattend file to your mounted image:

    ```
    DISM /Image=C:\mount\windows /Apply-Unattend=C:\mount\windows\Windows\Panther\unattend.xml
    ```

When the PC boots, it will boot into S mode with CI policies enforced.  If you need to make customizations to the Windows image, you'll have to enable the manufacturing registry key. This will allow you to make changes in audit mode.

### Add the manufacturing registry key

Enabling manufacturing mode is a step you'll have to do when working with Windows 10 in S mode and Windows 10 S. To enable customizations during the manufacturing process, you'll have to add a registry key that gives you the ability to run unsigned code when booted into audit mode. This can help you build and test your image when getting a PC ready to ship.

We'll add the customization registry key to the mounted image by loading the mounted image's SYSTEM registry hive, and then then adding a key. Then we'll configure ScanState to exclude the registry key when capturing your recovery package to ensure that the registry key doesn't get restored during reset or recovery scenarios.

> [!IMPORTANT]
> Don't ship your PC with the registry in place. Remove the registry key prior to shipping the device.

1. Load the SYSTEM registry hive from your mounted image into regedit on your technician PC. We'll use a temporary hive called HKLM\Windows10S.

    ```
	reg load HKLM\Windows10S C:\Mount\Windows\Windows\System32\Config\System
    ```

2. Add the following key to the registry have that you just mounted.

    ```
    reg add HKLM\Windows10S\ControlSet001\Control\CI\Policy /v ManufacturingMode /t REG_DWORD /d 1
    ```

3. Unload the registry hive from your technician PC.

    ```
    reg unload HKLM\Windows10S
    ```

The mounted image now has the manufacturing key that will allow you to make changes in audit mode. You'll have to remove it before shipping the PC.

To learn about the Windows 10 S manufacturing registry key, see [Windows 10 S manufacturing mode](windows-10-s-manufacturing-mode.md).

### Create exclusion.xml

Now we'll create a file that automates the exclusion of the customizations registry key when you capture settings for recovery. This ensures that your PC doesn't restore the customization registry key during the recovery process.

1. Create an xml file in a text editor.

2. Copy and paste the following code. This tells ScanState to not capture the registry key in the recovery package that it creates:

    ```
   &lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
   <migration urlid="http://www.microsoft.com/migration/1.0/migxmlext/ExcludeManufacturingMode">
   <component type="System">
    <displayName>Exclude manufacturing regkey</displayName>
        <role role="Settings">
            <rules context="System">
                <unconditionalExclude>
                    <objectSet>
                        <pattern type="Registry">HKLM\SYSTEM\CurrentControlSet\Control\CI\Policy [ManufacturingMode]</pattern>
                    </objectSet>
                </unconditionalExclude>
            </rules>
        </role>
   </component>
   </migration>
    ```

3. Save the file as exclusion.xml.

We'll use this config file when we capture a ScanState package for recovery later in the lab.

You can learn about excluding files and settings from a ScanState package at [Exclude Files and Settings](https://docs.microsoft.com/en-us/windows/deployment/usmt/usmt-exclude-files-and-settings).

## Add drivers

Like other versions of Windows, you can add drivers to a Windows 10 S image to ensure that hardware is setup and working the first time a user boots into Windows. Make sure that the drivers you add to your Windows 10 S are compatible with Windows 10 S and won't be blocked.

1.	Add a single driver to your Windows and WinRE images from an .inf file. In this example, we're using a driver named media1.inf:
	
    ```
    Dism /Add-Driver /Image:"C:\mount\windows" /Driver:"C:\Drivers\PnP.Media.V1\media1.inf"
    Dism /Add-Driver /Image:"C:\mount\winre" /Driver:"C:\Drivers\PnP.Media.V1\media1.inf"
    ```
    Where "C:\Drivers\PnP.Media.V1\media1.inf" is the .inf file for the driver you're adding.

    ```
    Dism /Add-Driver /Image:"C:\mount\windows" /Driver:c:\drivers /Recurse 
    ```

2.	Verify that the drivers are part of the images:
    ```
	Dism /Get-Drivers /Image:"C:\mount\windows"
    Dism /Get-Drivers /Image:"C:\mount\winre"
    ```
    Check the list of packages and verify that the list contains the drivers you added.
 
For more information about adding drivers to an offline Windows image, see [Add and Remove Drivers to an Offline Windows Image](add-and-remove-drivers-to-an-offline-windows-image.md).

## Add a language (optional)

In this section, we'll add the German (de-de) language pack to the mounted Windows and WinRE images.

1.	Add German language package to the Windows image.

    Use the language packs from the 64-bit ISO:
    
    ```
    Dism /Add-Package /Image:C:\mount\windows /PackagePath:"E:\x64\langpacks\Microsoft-Windows-Client-Language-Pack_x64_de-de.cab "
    ```
    Where E: is the drive letter of the mounted language pack ISO.

    
2. Add the German language pack to Windows RE. Language packs are available as part of the ADK, and ensure that a user's language is available during recovery scenarios.

    ```
    Dism /image:C:\mount\winre /add-package /packagepath:"E:\Windows Preinstallation Environment\x64\WinPE_OCs\de-de\lp.cab" 
    ```

See [Add and remove language packs offline using DISM](add-and-remove-language-packs-offline-using-dism.md) for more information.

## Add the latest General Distribution Release (GDR)

Install the latest GDR package that include the latest bug fixes and OS changes.

> **Important:** Install GDR packages **after** you install language packs, AppX packages, and Features on Demand. If you install a GDR prior to adding these, you'll have to reinstall the GDR.

1. Download the GDR (KB 4020102) from the [Microsoft Update Catalog](http://www.catalog.update.microsoft.com/Search.aspx?q=4020102).

2. Use DISM /add package to add the GDR to the mounted images

    ```
    dism /image:"C:\mount\windows" /add-package /packagepath:C:\temp\windows10.0-kb4020102-x64_9d406340d67caa80a55bc056e50cf87a2e7647ce.msu
    dism /image:"C:\mount\winre" /add-package /packagepath:C:\temp\windows10.0-kb4020102-x64_9d406340d67caa80a55bc056e50cf87a2e7647ce.msu
    ```

3. Use DISM to cleanup your image.
    
    ```
    DISM /Cleanup-Image /Image=C:\mount\winre /StartComponentCleanup /ScratchDir:C:\Temp
    ```

See [Add or remove packages offline using DISM](add-or-remove-packages-offline-using-dism.md) for more information about adding packages to your Windows image.

## Unmount WinRE Image and make a copy

Now that you have made all of your offline customizations, you can unmount your images.

1. Close all applications that might access files from the images.

2. Commit the changes and unmount the WinRE and Windows images:

    ```
    Dism /Unmount-Image /MountDir:"C:\mount\winre" /Commit
    Dism /Export-Image /SourceImageFile:c:\mount\windows\windows\system32\recovery\winre.wim /SourceIndex:1 /DestinationImageFile:c:\mount\winre-optimized.wim
    del c:\mount\windows\windows\system32\recovery\winre.wim
    copy c:\mount\winre-optimized.wim c:\mount\windows\windows\system32\recovery\winre.wim
    ```

## Unmount install.wim

```
Dism /Unmount-Image /MountDir:"C:\mount\windows" /Commit
```

## Copy install.wim and winre.wim to your USB drive

```
copy c:\temp\install.wim t:\
copy c:\temp\winre-optimized.wim t:\
```

## Deploy the image to reference PC

1. Boot your reference PC to WinPE.

2. Use the deployment scripts to apply your modified install.wim image.

    ```
    T:\Deployment\walkthrough-deploy.bat t:\install.wim
    ```

## Boot to audit mode and make changes

1. Boot your reference PC if it's not already booted.
2. When the device boots to OOBE, press Ctrl+Shift+F3 to enter Audit mode.
3. The PC will restart into audit mode.
4. Make changes to the PC. See the table on [Planning a Windows 10 in S mode image](windows-10-s-planning.md#customizations) to see which customizations are available in audit mode.

To learn about audit mode, see [Audit mode overview](audit-mode-overview.md).
To learn about Audit mode's behavior with Windows 10 S, see [Audit mode](windows-10-s-manufacturing-considerations.md#audit-mode) in [Windows 10 S manufacturing environment](windows-10-s-manufacturing-considerations.md).

## Capture your audit mode changes for the recovery tools

Now that you've customized your image in Audit mode, you can use ScanState to capture the package so the customizations are available in recovery scenarios.

1. Use ScanState that you copied to your USB key to capture customizations into a provisioning package. Use the exclusion.xml file that you created earlier to ensure that the manufacturing registry key is not restored during recovery.

    ```
    md c:\Recovery\Customizations
    T:\deploymenttools\scanstate /config:T:\deploymenttools\Config_SettingsOnly.xml /o /v:13 /ppkg c:\recovery\customizations\usmt.ppkg /i:exclusion.xml /l:C:\Scanstate.log
    ```


2. When the capture completes successfully, delete the ScanState logfile: `del c:\scanstate.log`.

## Remove the manufacturing registry key

When you're finished customizing your PC in audit mode, you have to remove the manufacturing registry key that allows you to run unsigned code on Windows 10 S. 

To remove the registry key, run the following command as administrator when booted into audit mode on the reference PC:

```
reg delete HKLM\system\ControlSet001\Control\CI\Policy /v ManufacturingMode
```

## Add WinRE back into your captured image

To ensure that your WinRE image is captured for your final deployment, copy your exported WinRE-optimized.wim image to your Windows 10 S image.

```
xcopy t:\winre-optimized.wim c:\windows\system32\recovery\winre.wim
```

## Sysprep and shut down the PC

1. Open Command Prompt.
2. Run sysprep to reseal the PC and make it ready for capture.
    ```
    c:\windows\system32\sysprep\sysprep /generalize /oobe /shutdown
    ```

## Capture the image

1. Boot the reference PC into WinPE.
2. Identify the drive letter of the Windows partition in diskpart:
    
    ```
    diskpart
    list volume
    exit
    ```

3. Use DISM to capture the Windows partition.

    ```
    dism.exe /capture-image /ImageFile:"T:\Images\Windows10S.wim" /capturedir:C:\ /Name:"Windows10S"
    ```
    Where C:\ is the Windows partition.

See [Capture and apply Windows system and recovery partitions](capture-and-apply-windows-system-and-recovery-partitions.md) for more information.

## Deploy your image and verify customizations and recovery

#### Apply your image

1. Boot your reference PC into WinPE.
2. Apply your Windows 10 in S mode image (Windows10S.wim) to the PC. This will overwrite any existing Windows installations.

    ```
    T:
    cd Deployment
    T:\Deployment\applyimage.bat T:\images\Windows10S.wim
    ```

### Verify customizations

1. Boot the reference PC. This is the first time booting the PC with your new Windows image.
2. If you installed additional languages, verify that these preinstalled languages appear and can be selected by the user during OOBE.
3. Validate the desktop customizations you made correctly after OOBE is complete.

### Verify recovery

To verify recovery is working as expected, perform the following validation tasks:

- Run refresh recovery and validate the user files are preserved and your factory desktop customizations are restored.
- Run reset recovery and validate the user files and profile are removed and your factory desktop customizations are restored.
- Validate extensibility scripts in the simulated RS3 enforcement level using the provided policy file.
- If you created a recovery package with ScanState, ensure that the manufacturing key was excluded when the package was captured.

## Ship the PC

Now that you have an image, you are ready to build and ship Windows 10 in S mode PCs. Make sure that the manufacturing registry key is removed and Secure Boot is enabled on shipped PCs.

