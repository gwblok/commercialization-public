---
Description: Install Windows from a USB Flash Drive
ms.assetid: b1ed80f1-cc1d-4eeb-9d5e-22c615479e1d
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Install Windows from a USB Flash Drive

ms.date: 01/31/2018
ms.topic: article


---

# Install Windows from a USB Flash Drive

Here's how to create a bootable Windows installation USB drive starting with a Windows .iso file or a Windows Setup DVD.

> [!Note]
> For new Windows 10 installations, we've got a tool that does this for you. See [Download Windows 10](https://www.microsoft.com/en-us/software-download/windows10).

## What you need

> [!div class="checklist"]
> * Windows 10 install .iso or DVD
> * USB flash drive with at least 5GB free space. This drive will be formatted, so make sure it doesn't have any important files on it.
> * Technician PC - Windows PC that you'll use to format the USB flash drive
> * Destination PC - A PC that you'll install Windows on

### Step 1 - Format the drive and set the primary partition as active

1.  Connect the USB flash drive to your technician PC.

2.  Open Disk Management: Right-click on **Start** and choose **Disk Management**.

3.  Format the partition: Right-click the USB drive partition and choose **Format**. Select the **FAT32** file system to be able to boot either BIOS-based or UEFI-based PCs.

4.  Set the partition as active: Right-click the USB drive partition and click **Mark Partition as Active**.

    > [!Note]
    > If **Mark Partition as Active** isn't available, you can instead use [diskpart](https://technet.microsoft.com/en-us/library/cc770877.aspx) to select the partition and mark it active.

### Step 2 - Copy Windows Setup to the USB flash drive

1.  Use File Explorer to copy and paste the entire contents of the Windows product DVD or ISO to the USB flash drive.

2.  Optional: add an unattend file to automate the installation process. For more information, see [Automate Windows Setup](windows-setup-automation-overview.md).

### Step 3 - Install Windows to the new PC

1.  Connect the USB flash drive to a new PC.

2.  Turn on the PC and press the key that opens the boot-device selection menu for the computer, such as the Esc/F10/F12 keys. Select the option that boots the PC from the USB flash drive.

    Windows Setup starts. Follow the instructions to install Windows.

3.  Remove the USB flash drive.

### Troubleshooting: file copy fails

This can happen when the Windows image file is over the FAT32 file size limit of 4GB. When this happens:

1. Copy everything except the Windows image file (sources\install.wim) to the USB drive (either drag and drop, or use this command, where D: is the mounted ISO and E: is the USB flash drive.)
   ```
   robocopy D: E: /s /max:3800000000
   ```

2. Split the Windows image file into smaller files, and put the smaller files onto the USB drive:
   ```
   Dism /Split-Image /ImageFile:D:\sources\install.wim /SWMFile:E:\sources\install.swm /FileSize:3800
   ```

   Note, Windows Setup automatically installs from this file, so long as you name it install.swm.

## <span id="related_topics"></span>Related topics


[Windows Setup Technical Reference](windows-setup-technical-reference.md)

 

 






