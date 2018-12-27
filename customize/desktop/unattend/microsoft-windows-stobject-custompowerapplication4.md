---
title: CustomPowerApplication4
description: CustomPowerApplication4
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 89057eb3-67a4-403f-8744-175eef412399
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# CustomPowerApplication4

`CustomPowerApplication4` specifies the fourth Battery Meter customized context menu item.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Application](microsoft-windows-stobject-custompowerapplication4-application.md) | Specifies the name and the path of the application to run. |
| [IconID](microsoft-windows-stobject-custompowerapplication4-iconid.md) | Specifies the optional icon resource ID. |
| [ItemName](microsoft-windows-stobject-custompowerapplication4-itemname.md) | Specifies the display text of the application. |
| [Parameters](microsoft-windows-stobject-custompowerapplication4-parameters.md) | Specifies the optional parameters to use when running the application. |

## Valid Configuration Passes

generalize

specialize

## Parent Hierarchy

[Microsoft-Windows-STObject](microsoft-windows-stobject.md) | **CustomPowerApplication4**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-STObject](microsoft-windows-stobject.md).

## XML Example

The following XML output shows how to configure `CustomPowerApplication4`.

```XML
<CustomPowerApplication4>
   <Application>C:\Program Files\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication4>
```

## Related topics

[Microsoft-Windows-STObject](microsoft-windows-stobject.md)
