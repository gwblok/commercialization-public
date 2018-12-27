---
title: InstalledBHOList
description: InstalledBHOList
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0d6d60cd-df48-4286-84d1-4208beef5a42
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# InstalledBHOList

`InstalledBHOList` contains settings for configuring Internet Explorer Browser Help Objects.

Browser Help Objects are add-on modules used to add functionality to Internet Explorer. Examples of Browser Help Objects include toolbars, animated mouse pointers, and stock tickers.

`InstalledBHOList` can contain one or more [AddonGuidItem](microsoft-windows-ie-internetexplorer-installedbholist-addonguiditem.md) settings each of which represents a single Browser Help Object. For more information, see the MSDN topic: [Building Browser Helper Objects](http://go.microsoft.com/fwlink/?LinkId=136975).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AddonGuidItem](microsoft-windows-ie-internetexplorer-installedbholist-addonguiditem.md) | Specifies settings for a Browser Help Object. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **InstalledBHOList**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example

The following XML output shows how to set two Internet Explorer Browser Help Objects.

```XML
<InstalledBHOList>
  <AddOnGuidItem>
    <AddOnGuid>{a1b1c123d1e1f4a5a6a7aa8a9a0a}</AddOnGuid>
  </AddOnGuidItem>
  <AddOnGuidItem>
    <AddOnGuid>{b1c123d1e1f4a5a6a7aa8a9a0a33}</AddOnGuid>
  </AddOnGuidItem>
</InstalledBHOList>
```

## Related topics

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

[InstalledBrowserExtensions](microsoft-windows-ie-internetexplorer-installedbrowserextensions.md)
