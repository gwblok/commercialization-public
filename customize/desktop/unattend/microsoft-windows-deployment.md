---
title: Microsoft-Windows-Deployment
description: Microsoft-Windows-Deployment
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c1fa294c-b5f8-4ffd-9dbb-4f39f6b4ee9e
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-Deployment

The Microsoft-Windows-Deployment component specifies settings related to auditing a computer.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AuditComputerName](microsoft-windows-deployment-auditcomputername.md) | Specifies the name of the computer being audited, and whether to restart the computer immediately after you specify this name. |
| [DeviceForm](microsoft-windows-deployment-deviceform.md) | Specifies the device form factor running the OS. |
| [DuplicatorDescription](microsoft-windows-deployment-duplicatordescription.md) | Specifies a description of the duplication tool used, as well as any other information that an OEM or an administrator stores in the registry. |
| [ExtendOSPartition](microsoft-windows-deployment-extendospartition.md) | Specifies whether to extend the partition on which you are installing Windows. |
| [Generalize](microsoft-windows-deployment-generalize.md) | Instructs Windows Setup to shut down the system after other answer-file settings are processed, and then to start the <strong>generalize</strong> configuration pass. |
| [Reseal](microsoft-windows-deployment-reseal.md) | Specifies whether the computer runs in audit mode or in Out-of-Box Experience (OOBE) when it next starts. |
| [RunAsynchronous](microsoft-windows-deployment-runasynchronous.md) | Specifies one or more commands to run asynchronously on the operating system during the specified configuration pass. |
| [RunSynchronous](microsoft-windows-deployment-runsynchronous.md) | Specifies one or more commands to run synchronously on the operating system during the specified configuration pass. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
