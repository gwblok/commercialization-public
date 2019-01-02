---
title: Create or Open a Distribution Share
description: Create or Open a Distribution Share
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 45bf648a-305b-43da-a22e-fd0cadddbf06
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Create or Open a Distribution Share

A distribution share is an optional storage folder for third-party drivers, applications, and packages that Microsoft issues (such as updates).

You can create a distribution-share folder by using Windows® System Image Manager (Windows SIM) or by using a manual technique. The procedures in this topic describe how to create, open, and explore a distribution-share folder.

> [!Note]
> You must use Windows SIM to add packages. For more information, see [Add Packages to a Distribution Share](add-packages-to-a-distribution-share.md).

## Create a distribution share using Windows SIM

1. Create a new folder where you want to place the distribution share. This folder can be on a network share (example: `\\server\share\MyDistributionShare`**) or on your local computer (example: `C:\MyDistributionShare`).
1. In the **Distribution Share** pane, right-click **Select a Distribution Share**, and then click **Create Distribution Share**. The **Create a Distribution Share** window appears.
1. Browse to the folder that you created, and then click **Open**. In the **Distribution Share** pane, the distribution-share folder opens. 
1. Windows SIM automatically creates a folder structure for the distribution share.

## Create a distribution share manually

1. In Windows Explorer, create a new folder where you want to place the distribution share. This folder can be on a network share (example: `\\server\share\MyDistributionShare`) or on your local computer (example: `C:\MyDistributionShare`).
1. In this folder, create the following subfolders:
    * `$OEM$`
    * `Packages`
    * `Out-of-Box Drivers`
    * `LangPacks`

> [!Note]
> Windows SIM recognizes only these subfolder names. For the distribution share to be valid, at least one of the four folders must be present. To enable Windows SIM to read the subfolder contents, the subfolder names must match this list exactly.

## Open a distribution share in Windows SIM

1. In the **Distribution Share** pane, click the top node of the currently open distribution share. Alternately, right-click **Select a Distribution Share**, and then click **Select Distribution Share**. The **Select a Distribution Share** dialog box opens.
1. Browse to the distribution share that you want to open. The distribution share can be opened only if the following folder structure exists:
    * `$OEM$`
    * `Packages`
    * `Out-of-Box Drivers`
    * `LangPacks`
1. Select the distribution share that you want to open, and then click **OK**. The distribution share opens in the **Distribution Share** pane.

## Explore a distribution share from Windows SIM

1. In Windows SIM, right-click the top node in the **Distribution Share** pane, and then click **Explore Distribution Share**.
1. The distribution-share folder opens in Windows Explorer, where you can modify files or move files between folders.

## Related topics

[Windows System Image Manager How-to Topics](windows-system-image-manager-how-to-topics.md)

[Manage Files and Folders in a Distribution Share](manage-files-and-folders-in-a-distribution-share.md)

[Add Packages to a Distribution Share](add-packages-to-a-distribution-share.md)
