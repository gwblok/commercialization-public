---
title: InstalledBrowserExtensions
description: InstalledBrowserExtensions
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7abd660b-13c4-4860-88d2-c67ddad32edc
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# InstalledBrowserExtensions

`InstalledBrowserExtensions` contains settings for configuring Internet Explorer Browser Extensions.

Browser Extensions are add-on modules used to add functionality to Internet Explorer. Examples of Browser Extensions include shortcut menu extensions, toolbars, explorer bars, and Browser Help Objects.

`InstalledBrowserExtensions` can contain one or more [AddonGuidItem](microsoft-windows-ie-internetexplorer-installedbrowserextensions-addonguiditem.md) settings, each of which represents a single Browser Extension.

For information about creating custom toolbars, see the MSDN topic: [Creating Custom Explorer Bars, Tool Bands, and Desk Bands](http://go.microsoft.com/fwlink/?LinkId=140376).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AddonGuidItem](microsoft-windows-ie-internetexplorer-installedbrowserextensions-addonguiditem.md) | Specifies settings for a Browser Extension. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **InstalledBrowserExtensions**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example

The following XML output shows how to set two Internet Explorer Browser Extensions.

```XML
<InstalledBrowserExtensions>
  <AddonGuidItem>
    <AddonGuid>{a1b1c123d1e1f4a5a6a7aa8a9a0a}</AddonGuid>
  </AddonGuidItem>
  <AddonGuidItem>
    <AddonGuid>{b1c123d1e1f4a5a6a7aa8a9a0a33}</AddonGuid>
  </AddonGuidItem>
</InstalledBrowserExtensions>
```

## Related topics

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

[InstalledBHOList](microsoft-windows-ie-internetexplorer-installedbholist.md)

[InstalledToolbarsList](microsoft-windows-ie-internetexplorer-installedtoolbarslist.md)

[PreApprovedAddons](microsoft-windows-ie-internetexplorer-preapprovedaddons.md)
