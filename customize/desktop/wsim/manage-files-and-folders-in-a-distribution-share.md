---
title: Manage Files and Folders in a Distribution Share
description: Manage Files and Folders in a Distribution Share
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: cb8681fd-e1cf-4c2c-9108-12c73ee49cc7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Manage Files and Folders in a Distribution Share

After a distribution-share folder is created, you can add files to the `$OEM$` or `Out-of-Box Drivers` folders. You cannot add packages directly to the Packages folder. You must use Windows® System Image Manager (Windows SIM) to add packages to a distribution share. For more information, see [Add Packages to a Distribution Share](add-packages-to-a-distribution-share.md).

You can make out-of-box device drivers (also called third-party drivers) available in Windows SIM by copying device drivers to the **Out-of-Box Drivers** folder in a distribution share. You can use subfolders to organize out-of-box drivers. When you add an **Out-of-Box Drivers** folder to an answer file, all drivers in the folder and subfolders are also added. After drivers are copied to the appropriate folder, they are available through Windows SIM and can be added to an answer file.

When you create a configuration set, you can use the `$OEM$` folder to copy scripts, binaries, and other files to Windows during installation. An answer file can reference files and folders stored in subfolders of `\$OEM$` can be referenced in an answer file. For more information, see [Create a Configuration Set](create-a-configuration-set.md).

> [!Important]
> Do not overwrite existing files carried and serviced by the operating system. Overwriting system files can cause the operating system to behave unpredictably and cause serious issues.

To manage files and folders in a distribution share:

1. Open a distribution share. For more information, see [Create or Open a Distribution Share](create-or-open-a-distribution-share.md).
2. Right-click the distribution share, and then click **Explore Distribution Share**.
3. Double-click either the `$OEM$` folder or the **Out-of-Box Drivers** folder. The folder opens.
4. Manage files and folders in the following ways:
   * Create subfolders by right-clicking in the folder, clicking **New**, and then clicking **Folder**.
   * Add files to the distribution share by copying files and pasting them in the folder.
   * Delete distribution-share contents by right-clicking a file or folder and then clicking **Delete**.
   * Add out-of-box drivers by copying the device-driver files to the **Out-of-Box Drivers** folder.
   * Add applications, scripts, or other files to the `$OEM$` subfolders.

     > [!Note]
     > The `$OEM$` subfolders are organized in a specific structure. Copy files to the `$OEM$` subfolders as described in [Distribution Shares and Configuration Sets Overview](distribution-shares-and-configuration-sets-overview.md). For example, if you add files to `$OEM$\$1\Program Files\Application1`, Windows Setup will copy them to `C:\Program Files\Application1` on the Windows installation.

5. Close the distribution-share folder.
6. The changes appear in the **Distribution Share** pane.

## Related topics

[Windows System Image Manager How-to Topics](windows-system-image-manager-how-to-topics.md)

[Create or Open a Distribution Share](create-or-open-a-distribution-share.md)

[Add Packages to a Distribution Share](add-packages-to-a-distribution-share.md)
