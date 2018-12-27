---
title: microsoft-windows-pnpcustomizationswinpe-
description: microsoft-windows-pnpcustomizationswinpe-
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7be7b298-fba8-4adf-8880-d3277c26cb61
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
Microsoft-Windows-PnpCustomizationsWinPE

The Microsoft-Windows-PnpCustomizationsWinPE component is used to add one or more out-of-box drivers to a Windows installation. Drivers that are located in the path specified by [DriverPaths](microsoft-windows-pnpcustomizationswinpe-driverpaths.md) are copied to the driver store of the Windows installation during the windowsPE configuration pass.

You can add boot-critical as well as non boot-critical drivers with this component to a Windows image before it is installed.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DriverPaths](microsoft-windows-pnpcustomizationswinpe-driverpaths.md) | Specifies one or more driver paths that contain out-of-box drivers. Drivers in this path are copied to the Windows image during the <strong>windowsPE</strong> configuration pass. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)

[Microsoft-Windows-PnpCustomizationsNonWinPE](microsoft-windows-pnpcustomizationsnonwinpe.md)
