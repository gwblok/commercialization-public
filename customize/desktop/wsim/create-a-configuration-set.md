---
title: Create a Configuration Set
description: Create a Configuration Set
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9f785225-1e42-4900-bd82-6ca3899b7ab0
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Create a Configuration Set

The following procedure describes how to create a configuration set by using Windows® System Image Manager (Windows SIM).

A configuration set is a smaller version of a distribution share and is more easily copied to removable media or a network share. It is a collection of files that have been converted to binary form. These files are a self-contained alternative to referencing a distribution share.

Because a configuration set contains only internal references, it can be used for both online and offline installations. It can also be duplicated and changed for different types of installations.

1. Open Windows SIM.
1. Open an answer file. For more information, see [Create or Open an Answer File](create-or-open-an-answer-file.md).
1. On the **Tools** menu, click **Create Configuration Set**. The **Create Configuration Set** window opens.
1. Browse to the destination folder for the configuration set, or enter a folder name.
1. Select a folder that you want to copy to your `$OEM$` folder (optional), and then click **OK**.

> [!Important]
> If a configuration set is used during Windows Setup, all of the contents at the root of the media where the answer file exists are copied to the Windows installation. If there are many files and folders at the same level as the answer file, Windows Setup copies all of the files and folders to the Windows installation. Note that this might slow down installation. In some cases, you might run out of disk space.

## Related topics

[Windows System Image Manager How-to Topics](windows-system-image-manager-how-to-topics.md)

[Manage Files and Folders in a Distribution Share](manage-files-and-folders-in-a-distribution-share.md)

[Add Packages to a Distribution Share](add-packages-to-a-distribution-share.md)

[Create or Open a Distribution Share](create-or-open-a-distribution-share.md)
