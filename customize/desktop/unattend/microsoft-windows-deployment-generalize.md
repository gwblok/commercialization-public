---
title: Generalize
description: Generalize
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 59d05509-75e6-404d-b3dd-139c78353cad
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Generalize

`Generalize` prepares the computer to be captured as a reference image immediately after other answer-file settings are processed. For more information about configuration passes, see [Windows Setup Configuration Passes](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/how-configuration-passes-work). To learn about generalizing a Windows installation, see [Sysprep (Generalize) a Windows installation](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/sysprep--generalize--a-windows-installation).

When `Generalize` is set, Windows Setup will:

1. Complete all of the other unattend settings in the configuration pass.
1. Run the **generalize** configuration pass.
1. Prepare the computer for imaging.

The following table provides scenarios for each combination of [Mode](microsoft-windows-deployment-generalize-mode.md) and [ForceShutdownNow](microsoft-windows-deployment-generalize-forceshutdownnow.md).

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mode value</th>
<th>ForceShutdownNow value</th>
<th>Result</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audit</p></td>
<td><p>false</p></td>
<td><p>Prepares the operating system to start in the <strong>auditSystem</strong> configuration pass, and then restarts the computer.</p></td>
</tr>
<tr class="even">
<td><p>Audit</p></td>
<td><p>true</p></td>
<td><p>Prepares the operating system to start in the <strong>auditSystem</strong> configuration pass, and then shuts the computer down immediately with no user interaction.</p></td>
</tr>
<tr class="odd">
<td><p>OOBE</p></td>
<td><p>false</p></td>
<td><p>Prepares the operating system to start in the <strong>oobeSystem</strong> configuration pass, and then restarts the computer.</p></td>
</tr>
<tr class="even">
<td><p>OOBE</p></td>
<td><p>true</p></td>
<td><p>Prepares the operating system to start in the <strong>oobeSystem</strong> configuration pass, and then shuts the computer down immediately with no user interaction.</p></td>
</tr>
</tbody>
</table>

> [!Note]
> Do not use this setting in conjunction with the [Reseal](microsoft-windows-deployment-reseal.md) setting. If you use both settings, the **Reseal** setting is ignored.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [ForceShutdownNow](microsoft-windows-deployment-generalize-forceshutdownnow.md) | Specifies whether the computer shuts down immediately after the <code>Mode</code> setting is applied. |
| [Mode](microsoft-windows-deployment-generalize-mode.md) | Specifies which configuration pass the computer start after the <strong>generalize</strong> configuration pass is complete. The options include: <strong>Audit</strong> or <strong>OOBE</strong>. |

## Valid Configuration Passes

auditUser

## Parent Hierarchy

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | **Generalize**

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

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md)
