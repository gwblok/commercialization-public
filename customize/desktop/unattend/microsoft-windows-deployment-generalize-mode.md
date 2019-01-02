---
title: Mode
description: Mode
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 469ea416-b9fb-45e2-b083-d305ada47b6a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Mode

`Mode` indicates whether, after completing other tasks, the computer returns to audit mode, or is set to start the Windows Out-of-Box Experience (OOBE). For more information about modes, see [Windows Setup Configuration Passes](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/how-configuration-passes-work).

`Generalize` is a special-case setting. It is processed after all other settings in that configuration pass.

## Values

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Audit</strong></p></td>
<td><p>Specifies that the computer starts in audit mode.</p></td>
</tr>
<tr class="even">
<td><p><strong>OOBE</strong></p></td>
<td><p>Specifies that the computer starts the Windows Out-of-Box Experience (OOBE).</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

The default value for `Mode` is **OOBE**.

## Valid Configuration Passes

auditUser

## Parent Hierarchy

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [Generalize](microsoft-windows-deployment-generalize.md) | **Mode**

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
