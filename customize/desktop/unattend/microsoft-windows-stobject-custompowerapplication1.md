---
title: CustomPowerApplication1
description: CustomPowerApplication1
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f804daba-bb40-4149-a49a-51a37af8bf08
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# CustomPowerApplication1

`CustomPowerApplication1` specifies the first Battery Meter customized context menu item.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Application](microsoft-windows-stobject-custompowerapplication1-application.md) | Specifies the name and the path of the application to run. |
| [IconID](microsoft-windows-stobject-custompowerapplication1-iconid.md) | Specifies the optional icon resource ID. |
| [ItemName](microsoft-windows-stobject-custompowerapplication1-itemname.md) | Specifies the display text of the application. |
| [Parameters](microsoft-windows-stobject-custompowerapplication1-parameters.md) | Specifies the optional parameters to use when running the application. |

## Valid Configuration Passes

generalize

specialize

## Parent Hierarchy

[Microsoft-Windows-STObject](microsoft-windows-stobject.md) | **CustomPowerApplication1**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-STObject](microsoft-windows-stobject.md).

## XML Example

The following XML output shows how to configure `CustomPowerApplication1`.

```XML
<CustomPowerApplication1>
   <Application>C:\Program Files\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication1>
```

## Related topics

[Microsoft-Windows-STObject](microsoft-windows-stobject.md)
