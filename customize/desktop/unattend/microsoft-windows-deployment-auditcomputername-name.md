---
title: Name
description: Name
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 741c0f2e-c55b-477c-a870-58b6aab2029d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Name


`Name` specifies the computer name to use during audit mode.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>name</em></p></td>
<td><p>Specifies the name of the computer. If you do not specify a name and the <a href="microsoft-windows-deployment-auditcomputername-mustreboot.md" data-raw-source="[MustReboot](microsoft-windows-deployment-auditcomputername-mustreboot.md)">MustReboot</a> setting is present, this setting is ignored. The <em>name</em> value is a string with a maximum length of 15 characters.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
If you do not specify this setting, the existing computer name is preserved.

If you specify a new computer name, you might have to restart the computer for it to take effect. If additional processing is dependent on the new computer name, set the [MustReboot](microsoft-windows-deployment-auditcomputername-mustreboot.md) value to **true** to restart the computer immediately.

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


auditSystem

## Parent Hierarchy


[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [AuditComputerName](microsoft-windows-deployment-auditcomputername.md) | **Name**

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

 

 







