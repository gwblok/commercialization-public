---
title: AddonGuidItem
description: AddonGuidItem
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6773df92-8d2b-4c97-938b-bac673e3d53c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# AddonGuidItem

`AddonGuidItem` contains settings for configuring an Internet Explorer Browser Help Object.

Browser Help Objects are plug-in modules used to add functionality to Internet Explorer. Examples of Browser Help Objects include toolbars, animated mouse pointers, and stock tickers.

`AddonGuidItem` contains settings for a single Browser Help Object.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AddonGuid](microsoft-windows-ie-internetexplorer-installedbholist-addonguiditem-addonguid.md) | Specifies a GUID for a Browser Help Object. |
 
## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [InstalledBHOList](microsoft-windows-ie-internetexplorer-installedbholist.md) | **AddonGuidItem**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example

The following XML output shows how to set two Internet Explorer Browser Help Objects.

```XML
<InstalledBHOList>
  <AddonGuidItem>
    <AddonGuid>{a1b1c123d1e1f4a5a6a7aa8a9a0a}</AddonGuid>
  </AddonGuidItem>
  <AddonGuidItem>
    <AddonGuid>{b1c123d1e1f4a5a6a7aa8a9a0a33}</AddonGuid>
  </AddonGuidItem>
</InstalledBHOList>
```

## Related topics

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)
