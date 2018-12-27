---
title: Microsoft-Windows-PnpSysprep
description: Microsoft-Windows-PnpSysprep
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1be14a5d-3fc1-4424-bfd0-fa5664ceb92c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-PnpSysprep

The Microsoft-Windows-PnpSysprep component specifies whether all Plug and Play information persists during the generalize configuration pass and the specialize configuration pass.

Typically, during the **generalize** configuration pass, all device information is removed from the reference computer.

During the **specialize** configuration pass, any Plug and Play devices that are detected on the destination computer are re-initialized. Any Plug and Play devices that are not detected are removed from the computer.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DoNotCleanUpNonPresentDevices](microsoft-windows-pnpsysprep-donotcleanupnonpresentdevices.md) | Specifies whether Plug and Play information persists on the destination computer during the following specialize configuration pass. |
| [PersistAllDeviceInstalls](microsoft-windows-pnpsysprep-persistalldeviceinstalls.md) | Specifies whether all Plug and Play information persists on the destination computer during the generalize configuration pass. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
