---
title: MustReboot
description: MustReboot
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b125b298-b51f-47e0-88be-922599b28cb7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# MustReboot


`MustReboot` specifies whether to restart the computer immediately after setting it to audit mode [Name](microsoft-windows-deployment-auditcomputername-name.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Immediately restarts the computer.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Does not immediately restart the computer. The new computer name cannot take effect until the computer is rebooted. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


auditSystem

## Parent Hierarchy


[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [AuditComputerName](microsoft-windows-deployment-auditcomputername.md) | **MustReboot**

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


[AuditComputerName](microsoft-windows-deployment-auditcomputername.md)

 

 







