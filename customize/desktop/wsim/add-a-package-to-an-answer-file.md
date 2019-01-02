---
title: Add a Package to an Answer File
description: Add a Package to an Answer File
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e2c075b2-330e-4bbc-80a3-4221e6d7274b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Add a Package to an Answer File

The following procedures describe how to add a package to an answer file by using Windows® System Image Manager (Windows SIM).

You can add a package to an answer file by using one of three options: from the **Insert** menu, from the **Windows Image** pane, or from an open distribution-share folder in the **Distribution Share** pane.

## Add a package from the Insert menu

1. Open Windows SIM.
1. Create or open an answer file. For more information, see [Create or Open an Answer File](create-or-open-an-answer-file.md).
1. Open a distribution share. For more information, see [Create or Open a Distribution Share](create-or-open-a-distribution-share.md).
1. On the **Insert** menu, click **Package(s)**. The **Select Package(s) to Insert** window opens.
1. Browse to the package that you want to add, and then click **Open**.
1. In the **Properties** pane, under **Settings**, select one of the following values for **Action**: **Install**, **Remove**, **Configure**, or **Stage**.

## Add a package from the Windows Image pane

1. Open Windows SIM.
1. Create or open an answer file. For more information, see [Create or Open an Answer File](create-or-open-an-answer-file.md).
1. Open a distribution share. For more information, see [Create or Open a Distribution Share](create-or-open-a-distribution-share.md).
1. In the **Windows Image** pane, select the **Packages** node. Expand the node, right-click the package that you want to add to the answer file, and then click **Add to Answer File**.
1. In the **Properties** pane, under **Settings**, choose one of the following values for **Action**: **Install**, **Remove**, **Configure**, or **Stage**.

## Add a package from a distribution share

1. Open Windows SIM.
1. Create or open an answer file. For more information, see [Create or Open an Answer File](create-or-open-an-answer-file.md).
1. Open a distribution share. For more information, see [Create or Open a Distribution Share](create-or-open-a-distribution-share.md).
1. Right-click the package that you want to add to the distribution share packages directory, and then click **Add to Answer File**. The package is added to the answer file in the packages section.
1. In the **Properties** pane, under **Settings**, choose one of the following values for **Action**: **Install**, **Remove**, **Configure**, or **Stage**.

## Related topics

[Windows System Image Manager How-to Topics](windows-system-image-manager-how-to-topics.md)

[Create or Open an Answer File](create-or-open-an-answer-file.md)

[Configure Components and Settings in an Answer File](configure-components-and-settings-in-an-answer-file.md)

[Validate an Answer File](validate-an-answer-file.md)

[Hide Sensitive Data in an Answer File](hide-sensitive-data-in-an-answer-file.md)

[Add a Device Driver Path to an Answer File](add-a-device-driver-path-to-an-answer-file.md)

[Add a Custom Command to an Answer File](add-a-custom-command-to-an-answer-file.md)

[Find a Component, Setting, or Package in Windows SIM](find-a-component-setting-or-package-in-windows-sim.md)
