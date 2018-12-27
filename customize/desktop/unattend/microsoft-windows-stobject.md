---
title: Microsoft-Windows-stobject
description: Microsoft-Windows-stobject
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1b95d74a-0b7e-4ec6-bbc3-29b178b6d13a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-STObject

The Microsoft-Windows-stobject component enables you to customize the power-management applications provided to end users. These power-management applications are displayed in the **Power Options** item in Control Panel and the battery meter located in the notification area.

You can display customized power plans and also add links to additional power-management software by using the settings in this component.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [FlyoutAutoPowerScheme](microsoft-windows-stobject-flyoutautopowerscheme.md) | Specifies the globally unique identifier (GUID) of the Battery Meter Fly-out Balanced power plan. |
| [FlyoutPowerSaverPowerScheme](microsoft-windows-stobject-flyoutpowersaverpowerscheme.md) | Specifies the GUID of the Battery Meter Fly-out Power Saver power plan. |
| [CustomPowerApplication1](microsoft-windows-stobject-custompowerapplication1.md) | Specifies the first Battery Meter custom context-menu item. |
| [CustomPowerApplication2](microsoft-windows-stobject-custompowerapplication2.md) | Specifies the second Battery Meter custom context-menu item. |
| [CustomPowerApplication3](microsoft-windows-stobject-custompowerapplication3.md) | Specifies the third Battery Meter custom context-menu item. |
| [CustomPowerApplication4](microsoft-windows-stobject-custompowerapplication4.md) | Specifies the fourth Battery Meter custom context-menu item. |
| [CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md) | Specifies the fifth Battery Meter custom context-menu item. |
| [CustomPowerApplication6](microsoft-windows-stobject-custompowerapplication6.md) | Specifies the sixth Battery Meter custom context-menu item. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Microsoft-Windows-PowerCPL](microsoft-windows-powercpl.md)

[Components](components-b-unattend.md)
