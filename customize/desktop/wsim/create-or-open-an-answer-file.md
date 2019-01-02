---
title: Create or Open an Answer File
description: Create or Open an Answer File
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0e4cbbb2-633a-49fc-8fe2-106005bf357b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Create or Open an Answer File

The following procedure describes how to create a new answer file or open an existing answer file by using Windows® System Image Manager (Windows SIM).

After you create or open an answer file, you can add settings and packages to it. For more information, see [Configure Components and Settings in an Answer File](configure-components-and-settings-in-an-answer-file.md) and [Add a Package to an Answer File](add-a-package-to-an-answer-file.md).

## Create an answer file

1. Open Windows SIM.
1. Open a Windows image. For more information, see [Open a Windows Image or Catalog File](open-a-windows-image-or-catalog-file.md).
1. In the **Answer File** pane, select the top node, and then right-click to select **New Answer File**.

## Open an existing answer file

1. Open Windows SIM.
1. Right-click the **Answer File** pane, and then click **Open Answer File**. The **Open** dialog box appears.
1. Browse to the existing answer file, and then click **Open**.

The answer file appears in the **Answer File** pane.

> [!Note]
> The Windows image file that generated the answer file also opens if it is still in its original location.

## Troubleshooting

In some cases, Windows SIM might display validation errors when opening an existing answer file. If this happens, try the following options:

* Problems with individual settings in an answer file appear in the Messages pane. Use this information to identify and address the problem.
* If the answer file opens, but all the settings are listed as “does not exist” in the Messages pane, then the file you’re using might be for the wrong PC architecture – for instance, your original answer file might be based on x86, and your Windows catalog file is amd64. To fix this, you can find and replace processorArchitecture="x86" for processorArchitecture="amd64" and re-open the file.
* If Windows SIM can’t open the file at all, this often means there’s some malformed XML in the answer file. You can often narrow down the problem by cutting out sections of the answer file, one large block at a time, and trying again to re-open the file.

## Related topics

[Windows System Image Manager How-to Topics](windows-system-image-manager-how-to-topics.md)

[Configure Components and Settings in an Answer File](configure-components-and-settings-in-an-answer-file.md)

[Validate an Answer File](validate-an-answer-file.md)

[Hide Sensitive Data in an Answer File](hide-sensitive-data-in-an-answer-file.md)

[Add a Device Driver Path to an Answer File](add-a-device-driver-path-to-an-answer-file.md)

[Add a Package to an Answer File](add-a-package-to-an-answer-file.md)

[Add a Custom Command to an Answer File](add-a-custom-command-to-an-answer-file.md)

[Find a Component, Setting, or Package in Windows SIM](find-a-component-setting-or-package-in-windows-sim.md)
