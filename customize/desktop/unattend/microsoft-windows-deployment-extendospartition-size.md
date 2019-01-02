---
title: Size
description: Size
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bc3a26af-dfa1-41d0-8510-cc03990db90a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Size


`Size` specifies the size of the extension. If `Size` and [Extend](microsoft-windows-deployment-extendospartition-extend.md) are present in the same configuration pass, an error is logged, and installation terminates.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Size</em></p></td>
<td><p>An integer that indicates the size of the extension, in megabytes. If the total value of the current size of the partition plus this setting exceeds the available space, then the partition is not extended.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
You can extend only NTFS file system partitions.

The partition that you plan on extending must have unpartitioned space available following it.

 

## Valid Configuration Passes


auditSystem

generalize

oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [ExtendOSPartition](microsoft-windows-deployment-extendospartition.md) | **Size**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

## XML Example


The following XML output shows a deployment with no asynchronous or synchronous commands.

```
<AuditComputerName>
   <MustReboot>true</MustReboot>
   <Name>MyComputer</Name>
</AuditComputerName>
<ExtendOSPartition>
   <Size>200</Size>
</ExtendOSPartition>
<Reseal>
   <ForceShutdownNow>true</ForceShutdownNow>
   <Mode>Audit</Mode>
</Reseal>
```

## Related topics


[ExtendOSPartition](microsoft-windows-deployment-extendospartition.md)

 

 







