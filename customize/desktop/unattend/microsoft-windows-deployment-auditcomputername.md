---
title: AuditComputerName
description: AuditComputerName
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f8a6f20e-056c-4d65-9a33-3f1e592f9854
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# AuditComputerName

`AuditComputerName` contains the settings to specify the name of the computer to use during audit mode, and whether to restart the computer immediately after you have specified this name.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [MustReboot](microsoft-windows-deployment-auditcomputername-mustreboot.md) | Specifies whether to restart the computer immediately after specifying the [Name](microsoft-windows-deployment-auditcomputername-name.md) setting. |
| [Name](microsoft-windows-deployment-auditcomputername-name.md) | Specifies the computer name to use during audit mode. |

## Valid Configuration Passes

auditSystem

## Parent Hierarchy

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | **AuditComputerName**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

## XML Example

The following XML output shows a deployment with no asynchronous or synchronous commands.

```XML
<AuditComputerName>
   <MustReboot>true</MustReboot>
   <Name>MyComputer</Name>
</AuditComputerName>
<ExtendOSPartition>
   <Extend>true</Extend>
</ExtendOSPartition>
<Reseal>
   <ForceShutdownNow>true</ForceShutdownNow>
   <Mode>Audit</Mode>
</Reseal>
```

## Related topics

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md)
