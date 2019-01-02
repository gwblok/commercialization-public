---
title: Add Packages to a Distribution Share
description: Add Packages to a Distribution Share
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ebe0bdbf-1d3f-471a-8e79-d424ac0006d7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Add Packages to a Distribution Share

Packages are groups of files that Microsoft provides. These groups of files include service packs, security updates, language packs, and modifications to Windows® features. You can add a package to a Windows installation by using an answer file, a configuration set, or a distribution share.

You must use Windows System Image Manager (Windows SIM) to import packages. After a package is imported and available in a distribution share, you can add the package to an answer file. For more information, see [Add a Package to an Answer File](add-a-package-to-an-answer-file.md).

> [!Note]
> For specific information about how to add language packs, see [Add Multilingual Support to a Windows Distribution](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/add-multilingual-support-to-a-windows-distribution).

To import a package to a distribution share:

1. Select and open a distribution share. For more information, see [Create or Open a Distribution Share](create-or-open-a-distribution-share.md).
1. On the **Tools** menu, click **Import Package(s)**. The **Select Package(s) to Import** window opens.
1. Browse to the file or folder, select the file or folder, and then click **Open** or **Open Folder**.

Windows SIM adds the selected package to the distribution-share folder. The newly added package is displayed under the **Packages** node in the **Distribution Share** pane.

## Related topics

[Windows System Image Manager How-to Topics](windows-system-image-manager-how-to-topics.md)

[Manage Files and Folders in a Distribution Share](manage-files-and-folders-in-a-distribution-share.md)
