---
title: Validate an Answer File
description: Validate an Answer File
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 82389009-0a96-4213-a2b1-17209ba670c2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Validate an Answer File

Before you can save an answer file, you must validate the settings. After you successfully validate an answer file, you can apply all the setting values in the answer file to the Windows® image.

1. Open Windows System Image Manager (Windows SIM).
1. Open a Windows image. For more information, see [Open a Windows Image or Catalog File](open-a-windows-image-or-catalog-file.md).
1. Create or open an answer file. For more information, see [Create or Open an Answer File](create-or-open-an-answer-file.md).
1. On the **Tools** menu, click **Validate Answer File**.

Windows SIM compares the setting values in the answer file with the available settings in the Windows image.

* If the answer passes validation, a message appears in the **Messages** pane on the **Validation** tab. This message verifies that no warnings or errors occurred in the answer file. Otherwise, error messages appear in the same location.
* If an error occurs, double-click the error in the **Messages** pane to browse to the setting.
* If no modifications have been made to component settings, the values of the component settings are not saved in the answer file.

## Related topics

[Windows System Image Manager How-to Topics](windows-system-image-manager-how-to-topics.md)

[Create or Open an Answer File](create-or-open-an-answer-file.md)

[Configure Components and Settings in an Answer File](configure-components-and-settings-in-an-answer-file.md)

[Hide Sensitive Data in an Answer File](hide-sensitive-data-in-an-answer-file.md)

[Add a Device Driver Path to an Answer File](add-a-device-driver-path-to-an-answer-file.md)

[Add a Package to an Answer File](add-a-package-to-an-answer-file.md)

[Add a Custom Command to an Answer File](add-a-custom-command-to-an-answer-file.md)

[Find a Component, Setting, or Package in Windows SIM](find-a-component-setting-or-package-in-windows-sim.md)
