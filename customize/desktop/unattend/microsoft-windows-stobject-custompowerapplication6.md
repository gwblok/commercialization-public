---
title: CustomPowerApplication6
description: CustomPowerApplication6
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f210ec64-91db-4054-a891-38b1607119ad
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# CustomPowerApplication6

`CustomPowerApplication6` specifies the sixth Battery Meter customized context menu item.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Application](microsoft-windows-stobject-custompowerapplication6-application.md) | Specifies the name and the path of the application to run. |
| [IconID](microsoft-windows-stobject-custompowerapplication6-iconid.md) | Specifies the optional icon resource ID. |
| [ItemName](microsoft-windows-stobject-custompowerapplication6-itemname.md) | Specifies the display text of the application. |
| [Parameters](microsoft-windows-stobject-custompowerapplication6-parameters.md) | Specifies the optional parameters to use when running the application. |

## Valid Configuration Passes

generalize

specialize

## Parent Hierarchy

[Microsoft-Windows-STObject](microsoft-windows-stobject.md) | **CustomPowerApplication6**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-STObject](microsoft-windows-stobject.md).

## XML Example

The following XML output shows how to configure `CustomPowerApplication6`.

```XML
<CustomPowerApplication6>
   <Application>C:\Program Files\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication6>
```

## Related topics

[Microsoft-Windows-STObject](microsoft-windows-stobject.md)
