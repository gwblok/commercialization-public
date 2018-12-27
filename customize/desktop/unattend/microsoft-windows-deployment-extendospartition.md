---
title: ExtendOSPartition
description: ExtendOSPartition
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 40b1e3fa-b695-40ed-8da1-75283d0c1c57
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# ExtendOSPartition

`ExtendOSPartition` specifies whether to extend the partition on which you are installing Windows. This setting is required for scenarios in which a customer has installed the Windows image by using a sector-based imaging solution and now plans on extending the partition.

These settings are valid only for NTFS file-system partitions.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Extend](microsoft-windows-deployment-extendospartition-extend.md) | Specifies whether to extend the partition to fill the entire hard disk. |
| [Size](microsoft-windows-deployment-extendospartition-size.md) | Specifies the size of the extension in megabytes. If the total value of the current size of the partition plus this setting exceeds the available space, then the partition is not extended. |

> [!Note]
> If both of these are set, an error is logged, and installation is terminated.

## Valid Configuration Passes

auditSystem

generalize

oobeSystem

specialize

## Parent Hierarchy

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | **ExtendOSPartition**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

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
