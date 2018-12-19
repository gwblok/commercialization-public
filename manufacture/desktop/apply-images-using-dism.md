---
author: kpacquer
Description: Apply Images Using DISM
ms.assetid: f9e0727d-a210-4efa-85af-5b222c53624e
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Apply Images Using DISM
ms.author: kenpacq
ms.date: 12/14/2018
ms.topic: article
---

# Apply Images Using DISM

Deploy Windows images captured from your reference computer to one or more destination computers. 

If you're deploying an image captured as a **.FFU file**, the image will format and apply partitions to the entire drive. To learn more, see [Deploy Windows using Full Flash Update (FFU)](deploy-windows-using-full-flash-update--ffu.md).

If you're deploying an image captured as a **.WIM file**, you'll need to wipe the disk, add drive partitions, apply the image, and set up system and recovery partitions. (Note, Microsoft Reserved partitions (MSR) are managed by the computer. Do not modify these partitions.)


## Apply the images

You can apply images using our [sample scripts](http://download.microsoft.com/download/3/F/2/3F2646EF-D589-498C-9F07-DE5549BE018E/USB-B.zip). These scripts work with both .WIM and .FFU images. Run `ApplyImage.bat` in the `Deployment` folder of the sample scripts download.

Or, use the steps in this section to create your own scripts.

### .FFU images
See [Windows Full Flash Update (FFU) images, Deploy FFU](deploy-windows-using-full-flash-update--ffu.md#DeployFFU)

## .WIM images

1. Boot the destination computer to Windows PE. For more information, see [Windows PE (WinPE) Technical Reference](winpe-intro.md).

2. Connect to the network distribution share, USB drive, or file location where your Windows image is stored. In this example, we connect the N: drive to a network share:

    ```
    net use n: \\server\share
    ```
    
    If prompted, provide your network credentials.

3. Wipe the disk and create partitions. 

   a. At the Windows PE command prompt, type `diskpart` to start the **Diskpart** tool.
   b. Create your partitions. The partition structure on the destination computer should match the partition structure of the reference computer. 

    For examples of recommended partition structures, see [Configure UEFI/GPT-Based Hard Drive Partitions](configure-uefigpt-based-hard-drive-partitions.md#relatedsamplefiles) (most common) and [Configure BIOS/MBR-Based Hard Drive Partitions](configure-biosmbr-based-hard-drive-partitions.md#relatedsamplefiles).

    > [Note
    > You can automate this task with the `diskpart /s <script>` command. For more information, see [Diskpart Command line syntax](http://go.microsoft.com/fwlink/?LinkId=128458).

5.  Use DISM to apply images to your Windows partition.

    For each partition that you apply an image to, run the **DISM** **/apply-image** /imageFile: *&lt;image\_file&gt;* /index:*&lt;index\_number&gt;* /ApplyDir:*&lt;image\_path&gt;* command.

    ```
    Dism /apply-image /imagefile:"N:\Images\my-windows-partition.wim" /index:1 /ApplyDir:C:\
    ```

    **Note**  If the DISM /Apply-Image command fails, make sure you’re using a [supported version of DISM](dism-supported-platforms.md) for that Windows image. For example, to apply a Windows 10 image, you’ll need the Windows 10 version of DISM.

6.  To set up a system partition, you can use BCDboot to copy a simple set of system files to a system partition. These files include boot configuration data (BCD) information that is used to start Windows:

    Use the BCDboot tool to copy common system partition files and to initialize boot configuration data:

    ```
    C:\Windows\System32\bcdboot C:\Windows /l en-US
    ```

    For more information about the BCDboot tool, see [BCDboot Command-Line Options](bcdboot-command-line-options-techref-di.md).

    **Note**  
    Alternatively, you can also set up the system partition by applying a .WIM image, for example:

    `Dism /apply-image /imagefile:N:\Images\my-system-partition.wim /index:1 /ApplyDir:S:\`

7.  Set up the [Windows Recovery Environment](deploy-windows-re.md).

At this point, you can optionally make more changes to the image (see [Service an applied Windows image](service-an-applied-windows-image.md)).

Or, just reboot the PC. After a setup period, Windows starts the Out of Box Experience (or [Audit Mode](boot-windows-to-audit-mode-or-oobe.md)).

> [!Note]
> If you receive the error message: **Bootmgr not found. Press CTRL+ALT+DEL**, this indicates that Windows cannot identify the boot information in the active partition. If you receive this error message, check the following:
> 
> -   Use the DiskPart tool to check to make sure that the system partition is set to Active.
> 
> -   Check to make sure that the active partition includes system files.

## <span id="related_topics"></span>Related topics


[Capture Images of Hard Disk Partitions Using DISM](capture-images-of-hard-disk-partitions-using-dism.md)

[Boot Windows to Audit Mode or OOBE](boot-windows-to-audit-mode-or-oobe.md)

[DISM Image Management Command-Line Options](dism-image-management-command-line-options-s14.md)

[Applying Images using a script](http://go.microsoft.com/fwlink/?LinkId=618399)

 

 






