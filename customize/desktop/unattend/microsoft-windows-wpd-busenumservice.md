---
title: Microsoft-Windows-WPD-BusEnumService
description: Microsoft-Windows-WPD-BusEnumService
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d3336b02-03e0-47ff-90a0-42ba6b8fcda0
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-WPD-BusEnumService

The `Microsoft-Windows-WPD-BusEnumService` component contains settings used to manage how the system searches for devices that use Media Transfer Protocol over Bluetooth (MTP/BT).

MTP/BT enables the computer to synchronize and transfer data between the computer and portable devices. For example, the computer may synchronize Windows Media Player music and playlists to a portable music device.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [BTSearchIntervalOnAC](microsoft-windows-wpd-busenumservice-btsearchintervalonac.md) | Specifies how often the computer will search for portable devices using MTP/BT while plugged in to AC power. |
| [BTSearchIntervalOnDC](microsoft-windows-wpd-busenumservice-btsearchintervalondc.md) | Specifies how often the computer will search for portable devices using MTP/BT while on battery power. |
| [RegCacheUpdated](microsoft-windows-wpd-busenumservice-regcacheupdated.md) | For Microsoft internal use only. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
