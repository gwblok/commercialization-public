---
title: AddonGuidItem
description: AddonGuidItem
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 843859f7-dc85-4fab-a08b-b709b1671de7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# AddonGuidItem

`AddonGuidItem` contains settings for configuring an Internet Explorer Browser Help Object.

Browser Extensions are plug-in modules used to add functionality to Internet Explorer. Examples of Browser Extensions include shortcut menu extensions, toolbars, explorer bars, and Browser Help Objects.

`AddonGuidItem` contains settings for a single Browser Extension.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AddonGuid](microsoft-windows-ie-internetexplorer-installedbrowserextensions-addonguiditem-addonguid.md) | Specifies a GUID for a Browser Extension. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [InstalledBrowserExtensions](microsoft-windows-ie-internetexplorer-installedbrowserextensions.md) | **AddonGuidItem**

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
