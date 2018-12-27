---
title: Microsoft-Windows-TabletPC-Platform-Input-Core
description: Microsoft-Windows-TabletPC-Platform-Input-Core
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 07f8a2de-f24a-45f8-9992-f0577016eee6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-TabletPC-Platform-Input-Core

The Microsoft-Windows-TabletPC-Platform-Input-Core component contains settings to adjust the Tablet PC user interface.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AssociationData](microsoft-windows-tabletpc-platform-input-core-associationdata.md) | A container for <code>AssociationData</code> list items. These list items help associate a Tablet PC digitizer with a monitor. |
| [HandwritingPanelDockedModeSet](microsoft-windows-tabletpc-platform-input-core-handwritingpaneldockedmodeset.md) | Specifies whether the handwriting panel is initially docked by default. |
| [LinearityData](microsoft-windows-tabletpc-platform-input-core-linearitydata.md) | A container for <code>DeviceElement</code> list items. These list items enable the input of linearity data for calibrating the digitizers on the device. |
| [MultiTouchEnabled](microsoft-windows-tabletpc-platform-input-core-multitouchenabled.md) | Specifies whether the touch input can receive multiple simultaneous responses. |
| [PanningDisabled](microsoft-windows-tabletpc-platform-input-core-panningdisabled.md) | Specifies whether an end user can scroll through a page by touching the screen and sliding their finger up or down. |
| [TouchGate](microsoft-windows-tabletpc-platform-input-core-touchgate.md) | Specifies whether the touch input is turned on or off for the device. |
| [TouchKeyboardAutoInvokeEnabled](microsoft-windows-tabletpc-platform-input-core-touchkeyboardautoinvokeenabled.md) | Specifies whether the touch keyboard is automatically invoked by default when there is no hardware keyboard connected and the device is in non-tablet mode. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
