---

Description: 'Deploy Windows faster on the factory floor by using the Full Flash Update (FFU) image format.'
ms.assetid: af2b402f-9a5c-4c6a-8852-61039e5bec2a
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Windows Full Flash Update (FFU) images'

ms.date: 10/17/2017
ms.topic: article


---

# Windows Full Flash Update (FFU) images

Deploy Windows faster on the factory floor by using the Full Flash Update (FFU) image format. FFU images allow you to apply an image of a physical drive, including Windows, recovery, and system partition information all at once directly to a different drive.

Unlike the file-based WIM format, FFU is a sector-based file container that stores one or more partitions. Sector-based imaging means that FFUs take less time to deploy, but have larger files sizes than WIMs. See [WIM vs. VHD vs. FFU: comparing image file formats](wim-vs-ffu-image-file-formats.md) for information about the differences between image formats.

Starting with Windows 10, version 1709, DISM has the ability to capture, deploy, and service FFUs, with the following limitations:
- The drive that an FFU is applied to has to be the same or larger than the drive it is captured from
- FFU captures of encrypted disks are not supported
- Captures of disks that have [Volume Shadow Copy Service (VSS)](https://technet.microsoft.com/en-us/library/ee923636.aspx) enabled are not supported
- Splitting compressed FFUs is not supported


## What you need to work with FFUs in Windows

To capture, deploy, and mount FFU images with DISM, you'll need to work in a Windows 10, version 1709 or later, or WinPE for Windows 10, version 1709 or later environment. 

To capture and deploy FFUs using the instructions below, you'll also need: 

- A Windows PC that has been [generalized with Sysprep](sysprep--generalize--a-windows-installation.md). We'll refer to this as the reference PC. For a walkthrough on how to create an image that's ready for deployment, see the [OEM deployment of Windows 10 lab](oem-deployment-of-windows-10-for-desktop-editions.md). If you're going to be deploying your FFU to a PC that has a larger hard drive than the drive that you're capturing, choose the options to not configure recovery when deploying your initial image. This allows you to expand your drive after you apply the FFU.
- A PC to deploy the FFU image to. We'll refer to this as the destination PC. The hard drive on this PC will be overwritten, so make sure you're using a PC that doesn't have any information you want to keep.
- The latest version of the ADK, from [Download the Windows ADK](https://developer.microsoft.com/en-us/windows/hardware/windows-assessment-deployment-kit)
- Bootable WinPE media for Windows 10, version 1803 or later. See [WinPE: Create USB bootable drive](winpe-create-usb-bootable-drive.md) for instructions on how to create WinPE Media.
- Storage
  - USB storage, formatted as NTFS with enough space to save the FFU. 16 GB is enough space to store an FFU of a basic Windows image. You can use the same USB drive for WinPE and storage if you follow the [instructions for creating a multipartiton USB drive](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive#prepare-a-usb-drive). For best performance, you want to maximize I/O between where your FFU is stored and the destination PC. For best performance use a USB 3.0 drive to store the image, and an internal SSD for the destination device.

    **or**
    
  - Network storage where you can keep your FFU image. For optimal performance, use a 1 Gb or faster network.

## Capture an FFU

1. Boot the reference PC using WinPE bootable media.

2. Identify the drive to which you'll be capturing the image from. You can use diskpart, or [add Windows PowerShell support to WinPE](winpe-adding-powershell-support-to-windows-pe.md) and use [Get-Disk](https://technet.microsoft.com/itpro/powershell/windows/storage/get-disk) for scriptability and more complex setups such as a server with multiple disks. 

    ```
    diskpart 
    list disk
    exit
    ```

    The output will list your drives. Make a note of the disk number in the `Disk ###` column. This is the value that you'll use when capturing your image.

    ```
    DISKPART> list disk

    Disk ###  Status         Size     Free     Dyn  Gpt
    --------  -------------  -------  -------  ---  ---
    Disk 0    Online          238 GB      0 B        *
    Disk 1    Online           28 GB      0 B

    DISKPART>
    ```

3. Use DISM to capture an image of all the partitions on the physical drive. For *disk X:*, the string used with `/capturedrive` will look like this: `\\.\PhysicalDriveX`, where *X* is the disk number that diskpart provides. For example, to capture Disk 0, you'd use `/CaptureDrive:\\.\PhysicalDrive0`.

    For more information about PhysicalDrive*X*, see [CreateFile function](https://msdn.microsoft.com/library/windows/desktop/aa363858.aspx). 
    
    To see command line options for capturing FFUs, run `dism /capture-ffu /?` or see [DISM Image Management Command-Line Options](dism-image-management-command-line-options-s14.md). Note that you shouldn't have to specify a PlatformID when capturing a desktop image.

    The following command captures an FFU image of PhysicalDrive0 called WinOEM.ffu. The /name and /description arguments allow you to set information about your image. This information is displayed when you use `dism /get-imageinfo`. /name is required, /description is optional. 

    ```
    DISM.exe /capture-ffu /imagefile=e:\WinOEM.ffu /capturedrive=\\.\PhysicalDrive0 /name:disk0 /description:"Windows 10 FFU"
    ```

    This command also gives a name and description to the FFU image. Name is a required parameter.

## <span id="DeployFFU"></span>Deploy Windows from WinPE using an FFU

1. Boot your destination PC to WinPE.

2. Connect a storage drive or map the network location that has your FFU file and note the drive letter, for example, N.

3. Identify the drive to which you'll be applying the image:

   ```
   diskpart 
   list disk
   exit
   ```
   Note the drive number in the `Disk ###` column.

4. Apply the image to the cleaned drive. Here, we're applying n:\WinOEM.ffu to Disk 0.
    
   ```
   DISM /apply-ffu /ImageFile=N:\WinOEM.ffu /ApplyDrive:\\.\PhysicalDrive0
   ```

   To see the commands available with /apply-ffu, run `dism /apply-ffu /?` or see [DISM Image Management Command-Line Options](dism-image-management-command-line-options-s14.md).

5. Optional. Resize the Windows partition on the destination PC.

    If the reference PC and the destination PC have different sized hard drives, you'll have to resize the destination PC's Windows partition. The applied FFU will have the same partition sizes and layout as the reference PC, so you'll need to expand the Windows partition to take advantage of the additional space on the destination PC. If the Windows partition is not the last partition on the drive, you won't be able to easily extend the Windows partition. The below instructions assume that the Windows partition is the last partition on the drive. 
    
    > [!Note]
    > If you're going to be capturing an FFU from a smaller drive than the drive it will be applied to, make sure that the Windows partition is the last partition on the drive. ApplyImage.bat in the [Sample scripts](windows-deployment-sample-scripts-sxs.md) from the the [OEM Windows desktop deployment and imaging lab](oem-windows-deployment-and-imaging-walkthrough.md) gives you the ability to deploy Windows for this scenario.

   1. In WinPE on your destination PC, identify the volume of the Windows partiton that you have applied.
    
      ```
      diskpart
      list volume
      ```

   2. Select the volume of the Windows partition. We'll use `Volume 0` in our example.

      ```
      select volume 0
      ```

   3. Extend the partition to fill the unused space, and exit Diskpart.

      ```
      extend
      exit
      ````

## Mount an FFU for servicing

You can use DISM to mount FFU images for servicing. Like with other image formats, you can mount and modify an FFU before committing changes and unmounting. Mounting an FFU for servicing uses the same `/mount-image` command that you use for mounting other image types. When mounting an FFU, you'll always use `/index:1` when mounting.

Unlike WIM images, FFU images get mounted as virtual hard disks. Files appear in the specified mount folder, but since FFUs can contain more than one partition but only have one index, DISM maps only the Windows partition from the mounted FFU to the mount folder.

To mount an FFU

1. Open a Command Prompt as administrator.

2. Mount the image using `dism /mount-image`. This example mounts D:\WinOEM.ffu to C:\ffumount:

    ```
    dism /mount-image /imagefile:"D:\WinOEM.ffu" /mountdir:"C:\ffumount" /index:1
    ```

    To see available command line options for `/mount-image` run `dism /mount-image /?` or see [DISM image management command line options](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14#mount-image).

3. Service your image. For example, to enable the legacy components feature:

    ```
    dism /image:"C:\ffumount" /enable-feature:legacycomponents
    ```

    To see available options, run `dism /image:<path to mounted image> /?` or 

4. Unmount your FFU image and commit or discard changes. If you use /commit, your changes will be saved to your FFU file.

    To unmount your FFU and commit changes, you'd use `/unmount-image` with the `/commit` option:

    ```
    dism /unmount-image /mountdir:"C:\ffumount" /commit
    ```

    If you decide to not keep the changes you've made to the FFU, you can use `/unmount-image` with the `/discard` option:

    ```
    dism /unmount-image /mountdir:"C:\ffumount" /discard
    ```

## <span id="related_topics"></span>Related topics

[Download and install the Windows ADK](https://msdn.microsoft.com/windows/hardware/commercialize/adk-install)

[FFU image format](../mobile/ffu-image-format.md)

[WIM vs. VHD vs. FFU: comparing image file formats](wim-vs-ffu-image-file-formats.md)

[Planning a Multicast Strategy in Configuration Manager](http://go.microsoft.com/fwlink/?LinkId=286313)

[Capture and Apply Windows, System, and Recovery Partitions](capture-and-apply-windows-system-and-recovery-partitions.md)

[DISM Image Management Command-Line Options](dism-image-management-command-line-options-s14.md)

[CreateFile function](https://msdn.microsoft.com/library/windows/desktop/aa363858.aspx)