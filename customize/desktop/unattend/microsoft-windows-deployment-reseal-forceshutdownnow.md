---
title: ForceShutdownNow
description: ForceShutdownNow
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a82db5df-747b-40f5-bf6b-257bf8f49f57
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ForceShutdownNow


`ForceShutdownNow` modifies the `Reseal` setting, and specifies whether the computer shuts down immediately after the setting is applied.

`Reseal` is a special-case setting. It is processed before any other setting in the configuration pass. In some scenarios, it instructs Windows Setup either to process or to ignore all other settings in that configuration pass before starting another configuration pass. The following table provides scenarios for each combination of configuration pass, mode, and forced-shutdown behavior. When a configuration pass has more than one result, the table lists the results in the order that they take place.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuration pass</th>
<th>Mode value</th>
<th>ForceShutdownNow value</th>
<th>Result</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>auditSystem</strong></p></td>
<td><p><strong>Audit</strong></p></td>
<td><p><strong>false</strong></p></td>
<td><p>Starts the <strong>auditSystem</strong> configuration pass.</p></td>
</tr>
<tr class="even">
<td><p><strong>auditSystem</strong></p></td>
<td><p><strong>Audit</strong></p></td>
<td><p><strong>true</strong></p></td>
<td><div class="alert">
<strong>Caution</strong><br/><p>Unsupported, do not use. Sets the computer into a loop of reboots.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>auditSystem</strong></p></td>
<td><p><strong>OOBE</strong></p></td>
<td><p><strong>false</strong></p></td>
<td><ol>
<li><p>Ignores all other settings in the <strong>auditSystem</strong> configuration pass.</p></li>
<li><p>Starts the <strong>oobeSystem</strong> configuration pass.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>auditSystem</strong></p></td>
<td><p><strong>OOBE</strong></p></td>
<td><p><strong>true</strong></p></td>
<td><ol>
<li><p>Ignores all other settings in the <strong>auditSystem</strong> configuration pass.</p></li>
<li><p>Prepares Windows Setup to start the <strong>oobeSystem</strong> configuration pass.</p></li>
<li><p>Shuts the computer down immediately with no end-user interaction.</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>auditUser</strong></p></td>
<td><p><strong>Audit</strong></p></td>
<td><p><strong>false</strong></p></td>
<td><ol>
<li><p>Processes all other settings in the <strong>auditUser</strong> configuration pass.</p></li>
<li><p>Prepares Windows Setup to start the <strong>auditSystem</strong> configuration pass.</p></li>
<li><p>Restarts the computer.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>auditUser</strong></p></td>
<td><p><strong>Audit</strong></p></td>
<td><p><strong>true</strong></p></td>
<td><ol>
<li><p>Processes all other settings in the <strong>auditUser</strong> configuration pass.</p></li>
<li><p>Prepares Windows Setup to start the <strong>auditSystem</strong> configuration pass.</p></li>
<li><p>Shuts the computer down immediately with no end-user interaction.</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>auditUser</strong></p></td>
<td><p><strong>OOBE</strong></p></td>
<td><p><strong>false</strong></p></td>
<td><ol>
<li><p>Processes all other settings in the settings settings in the <strong>auditUser</strong> configuration pass.</p></li>
<li><p>Prepares Windows Setup to start the <strong>oobeSystem</strong> configuration pass.</p></li>
<li><p>Restarts the computer.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>auditUser</strong></p></td>
<td><p><strong>OOBE</strong></p></td>
<td><p><strong>true</strong></p></td>
<td><ol>
<li><p>Processes all other settings in the <strong>auditUser</strong> configuration pass.</p></li>
<li><p>Prepares Windows Setup to start the <strong>oobeSystem</strong> configuration pass.</p></li>
<li><p>Shuts the computer down immediately with no end-user interaction.</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>oobeSystem</strong></p></td>
<td><p><strong>Audit</strong></p></td>
<td><p><strong>false</strong></p></td>
<td><ol>
<li><p>Ignores all other settings in the <strong>oobeSystem</strong> configuration pass.</p></li>
<li><p>Starts the <strong>auditSystem</strong> configuration pass.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>oobeSystem</strong></p></td>
<td><p><strong>Audit</strong></p></td>
<td><p><strong>true</strong></p></td>
<td><ol>
<li><p>Ignores all other settings in the <strong>oobeSystem</strong> configuration pass.</p></li>
<li><p>Prepares Windows Setup to start the <strong>auditSystem</strong> configuration pass.</p></li>
<li><p>Shuts the computer down immediately with no end-user interaction.</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>oobeSystem</strong></p></td>
<td><p><strong>OOBE</strong></p></td>
<td><p><strong>false</strong></p></td>
<td><p>Starts the <strong>oobeSystem</strong> configuration pass.</p></td>
</tr>
<tr class="even">
<td><p><strong>oobeSystem</strong></p></td>
<td><p><strong>OOBE</strong></p></td>
<td><p><strong>true</strong></p></td>
<td><div class="alert">
<strong>Caution</strong><br/><p>Unsupported, do not use. Sets the computer into a loop of reboots.</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



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
<p>This is the default setting.</p></td>
</tr>
</tbody>
</table>



## Valid Configuration Passes


auditSystem

auditUser

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [Reseal](microsoft-windows-deployment-reseal.md) | **ForceShutdownNow**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

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


[Reseal](microsoft-windows-deployment-reseal.md)

[Mode](microsoft-windows-deployment-reseal-mode.md)

[Configuration Passes](http://go.microsoft.com/fwlink/?LinkId=268344)











