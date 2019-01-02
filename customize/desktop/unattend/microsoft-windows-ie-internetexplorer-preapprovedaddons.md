---
title: PreApprovedAddons
description: PreApprovedAddons
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 95143c24-f5be-45e5-8028-4b254692797b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# PreApprovedAddons

> [!Important]
> This setting has been deprecated in Windows 8.1. The information about this deprecated setting is provided for reference only. Add-ons can still be installed but they will be disabled, by default. Users will be able to choose the add-ons to enable.

`PreapprovedAddons` contains settings for configuring Internet Explorer pre-approved add-ons.

Pre-approved add-ons are plug-in modules used to add functionality to Internet Explorer.

`PreapprovedAddons` can contain one or more [AddonGuidItem](microsoft-windows-ie-internetexplorer-preapprovedaddons-addonguiditem.md) settings each of which represents a single add-on module.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AddonGuidItem](microsoft-windows-ie-internetexplorer-preapprovedaddons-addonguiditem.md) | Specifies settings for an add-on module. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **PreapprovedAddons**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example

The following XML output shows how to set two Internet Explorer pre-approved add-ons.

```XML
<PreapprovedAddons>
  <AddonGuidItem>
    <AddonGuid>{a1b1c123d1e1f4a5a6a7aa8a9a0a}</AddonGuid>
  </AddonGuidItem>
  <AddonGuidItem>
    <AddonGuid>{b1c123d1e1f4a5a6a7aa8a9a0a33}</AddonGuid>
  </AddonGuidItem>
</PreapprovedAddons>
```

## Related topics

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

[InstalledBHOList](microsoft-windows-ie-internetexplorer-installedbholist.md)

[InstalledBrowserExtensions](microsoft-windows-ie-internetexplorer-installedbrowserextensions.md)

[InstalledToolbarsList](microsoft-windows-ie-internetexplorer-installedtoolbarslist.md)
