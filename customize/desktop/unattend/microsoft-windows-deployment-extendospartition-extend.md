---
title: Extend
description: Extend
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 24b1b2c1-26e7-4d1b-8b09-8f0b11499e16
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Extend


`Extend` indicates whether to extend the partition to fill the remaining space on the hard disk. If this setting and [Size](microsoft-windows-deployment-extendospartition-size.md) are present in the same configuration pass, an error is logged, and installation is terminated.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the partition is extended to fill the remaining space on the disk.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the partition is not extended. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
You can extend only NTFS file-system partitions.

 

## Valid Configuration Passes


auditSystem

generalize

oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [ExtendOSPartition](microsoft-windows-deployment-extendospartition.md) | **Extend**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

## XML Example


The following XML output shows a deployment with no asynchronous or synchronous commands.

```
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


[ExtendOSPartition](microsoft-windows-deployment-extendospartition.md)

 

 







