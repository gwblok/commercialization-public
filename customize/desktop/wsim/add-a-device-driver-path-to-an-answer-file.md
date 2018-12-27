---
title: Add a Device Driver Path to an Answer File
description: Add a Device Driver Path to an Answer File
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: fbb67511-d26d-40b1-b5b6-a923ca4dc8ad
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Add a Device Driver Path to an Answer File

The following procedure describes how to add a device driver path to an answer file by using Windows® System Image Manager (Windows SIM).

This device-driver path is used to process additional out-of-box device drivers during Windows Setup. Out-of-box device drivers can be copied to a Windows image during the **windowsPE** configuration pass. In this configuration pass, you can add boot-critical drivers to a Windows image before that image is installed.

> [!Note]
> You can add more drivers to the Windows installation during the **auditSystem** configuration pass.

When you select a driver path, you select a folder that contains one or more .inf drivers. The folder path is added to the answer file and, during an unattended installation, is referenced to find all drivers in the path and install them.

You can add only .inf drivers to a Windows image by using this procedure. You must install drivers that are packaged as a .exe file or other file types on a running Windows operating system.

To add a device-driver path to an answer file:

1. Open Windows SIM.
2. Create or open an answer file. For more information, see [Create or Open an Answer File](create-or-open-an-answer-file.md).
3. On the **Insert** menu, click **Driver Path**.
4. Select the configuration pass in which you want to install the driver. This can be the **windowsPE** or the **auditSystem** configuration pass.

   > [!Note]
   > Adding a driver to the **auditSystem** configuration pass processes the driver during Audit mode only.

5. The **Browse for Folder** dialog box appears. Select the driver path that you want to add to the answer file, and then click **OK**. The driver path is added to the answer file under the configuration pass that you selected. Depending on the configuration pass that you selected, the driver path is included as a list item to one of the following components:
   * **Microsoft-Windows-PnpCustomizationsWinPE** for the **windowsPE** configuration pass
   * **Microsoft-Windows-PnpCustomizationsNonWinPE** for the **auditSystem** configuration pass

     > [!Note]
     > You can also drag drivers from an **Out-of-Box Drivers** folder in the **Distribution Share** pane to either the **windowsPE** or **auditSystem** configuration pass in the **Answer File** pane. Or, right-click to add it.

## Related topics

[Windows System Image Manager How-to Topics](windows-system-image-manager-how-to-topics.md)

[Create or Open an Answer File](create-or-open-an-answer-file.md)

[Configure Components and Settings in an Answer File](configure-components-and-settings-in-an-answer-file.md)

[Validate an Answer File](validate-an-answer-file.md)

[Hide Sensitive Data in an Answer File](hide-sensitive-data-in-an-answer-file.md)

[Add a Package to an Answer File](add-a-package-to-an-answer-file.md)

[Add a Custom Command to an Answer File](add-a-custom-command-to-an-answer-file.md)

[Find a Component, Setting, or Package in Windows SIM](find-a-component-setting-or-package-in-windows-sim.md)
