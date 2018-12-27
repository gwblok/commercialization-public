---
title: Microsoft-Windows-SystemMaintenanceService
description: Microsoft-Windows-SystemMaintenanceService
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 678d8433-eb75-4188-a4fe-97d252f6dc13
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-SystemMaintenanceService

Microsoft-Windows-SystemMaintenanceService configures flash storage devices to be used as supplemental memory caches. This is typically used for devices that have been integrated with the computer, such as internal flash devices or solid-state drives (SSDs).

This component can improve system responsiveness, especially on systems with lower RAM or slower disks.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [CacheList](microsoft-windows-systemmaintenanceservice-cachelist.md) | Specifies settings for Microsoft ReadyBoost™ devices on the computer. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
