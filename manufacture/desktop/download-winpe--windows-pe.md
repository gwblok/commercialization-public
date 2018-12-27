---

Description: 'Download WinPE (Windows PE)'
ms.assetid: e1b5bcac-761f-4efb-9288-a20da1086446
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Download WinPE (Windows PE)'

ms.date: 11/07/2017
ms.topic: article
ms.custom: RS5
---

# Download WinPE (Windows PE)


Before you can use [WinPE,](winpe-intro.md) you'll have to create a bootable WinPE USB flash drive, CD, DVD, or virtual hard drive.

The files you need to create WinPE media are included in the [Winpe Add-on](https://go.microsoft.com/fwlink/?linkid=2022233) to the [Windows Assessment and Deployment Kit](http://go.microsoft.com/fwlink/?LinkId=526803). To create WinPE media, you'll have to [install the ADK](https://docs.microsoft.com/en-us/windows-hardware/get-started/adk-install) with the **Deployment tools** option, and then install the WindowsPE addon kit.

## Download and Install the Windows ADK

### For the ADK for Windows 10, version 1809

To start working with WinPE, download and install both the Windows Assessment and Deployment Kit (ADK) and the WinPE Add-ons.

> [!div class="nextstepaction"]
> [Download the Windows ADK for Windows 10, version 1809](https://go.microsoft.com/fwlink/?linkid=2026036)

 During installation, select **Deployment Tools**.

> [!div class="nextstepaction"]
> [Download the Windows PE add-on for the ADK](https://go.microsoft.com/fwlink/?linkid=2022233)

### For the ADK for Windows 10, version 1803 or earlier

In previous versions, WinPE is included in the [Windows ADK](http://go.microsoft.com/fwlink/?LinkId=526803). 

During installation, select the following features:

-   **Deployment Tools**: includes the **Deployment and Imaging Tools Environment**.

-   **Windows Preinstallation Environment**: includes the files used to install Windows PE.

## Next Steps - create a bootable USB, CD, or DVD:

After you've downloaded and installed the ADK, you can create bootable WinPE media.

- To learn how to create a bootable WinPE USB drive, see [WinPE: Create USB Bootable drive](winpe-create-usb-bootable-drive.md) 

- To learn how to create a bootable WinPE CD, DVD, ISO, or VHD, see [WinPE: Create a Boot CD, DVD, ISO, or VHD](winpe-create-a-boot-cd-dvd-iso-or-vhd.md)

## <span id="related_topics"></span>Related topics


[WinPE for Windows 10](winpe-intro.md)

[WinPE: Mount and Customize](winpe-mount-and-customize.md)
