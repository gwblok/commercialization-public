---
title: ForceShutdownNow
description: ForceShutdownNow
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a2bad325-372f-43ce-85d1-827aa0c07f61
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# ForceShutdownNow

`ForceShutdownNow` specifies whether the computer shuts down immediately after the **generalize** configuration pass is complete. For more information about modes, see [Windows Setup Configuration Passes](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/how-configuration-passes-work).

`Generalize` is a special-case setting. It is processed after all other answer-file settings in that configuration pass.

## Values

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>The computer shuts down immediately after the <code>Mode</code> setting is applied.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>The computer does not shut down immediately after the <code>Mode</code> setting is applied.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

## Valid Configuration Passes

auditUser

## Parent Hierarchy

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [Generalize](microsoft-windows-deployment-generalize.md) | **ForceShutdownNow**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

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
<Generalize>
   <ForceShutdownNow>true</ForceShutdownNow>
   <Mode>Audit</Mode>
</Generalize>
```

## Related topics

[Reseal](microsoft-windows-deployment-reseal.md)
