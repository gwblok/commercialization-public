---
title: Microsoft-Windows-PnpCustomizationsNonWinPE
description: Microsoft-Windows-PnpCustomizationsNonWinPE
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b85f64a4-3e3f-4472-abf3-7d1cecb37a89
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-PnpCustomizationsNonWinPE

The Microsoft-Windows-PnpCustomizationsNonWinPE component is used to add one or more out-of-box drivers to a Windows installation. Drivers located in the path specified by [DriverPaths](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths.md) are copied to the driver store of the Windows installation during the auditSystem configuration pass. When the system runs Plug and Play, these out-of-box drivers are available to install hardware on the computer.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DriverPaths](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths.md) | Specifies one or more driver paths that contain out-of-box drivers. Drivers in this path are copied to the Windows image during the <strong>auditSystem</strong> configuration pass. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)

[Microsoft-Windows-PnpCustomizationsWinPE](microsoft-windows-pnpcustomizationswinpe.md)
