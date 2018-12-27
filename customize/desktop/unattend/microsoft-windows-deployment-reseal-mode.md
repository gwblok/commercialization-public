---
title: Mode
description: Mode
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ec55a434-a244-43eb-ae14-75f085684518
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Mode


`Mode` is used with the [ForceShutdownNow](microsoft-windows-deployment-reseal-forceshutdownnow.md) setting to indicate whether the computer starts in audit mode or Out-of-Box-Experience (OOBE). For more information about modes, see the [Configuration Passes](http://go.microsoft.com/fwlink/?LinkId=268344) topic.

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
<strong>Caution</strong><br/><p>Unsupported. Do not use. Sets the computer into a loop of reboots.</p>
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
<li><p>Processes all other settings in the <strong>auditUser</strong> configuration pass.</p></li>
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
<strong>Caution</strong><br/><p>Unsupported. Do not use. Sets the computer into a loop of reboots.</p>
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
<td><p><strong>Audit</strong></p></td>
<td><p>Specifies that the computer starts in audit mode.</p></td>
</tr>
<tr class="even">
<td><p><strong>OOBE</strong></p></td>
<td><p>Specifies that the computer starts in OOBE mode.</p></td>
</tr>
<tr class="odd">
<td><p>(no value / default)</p></td>
<td><ul>
<li><p>During the <strong>auditSystem</strong> configuration pass, if <code>Mode</code> is not specified, then <code>Mode</code> defaults to <strong>Audit</strong>.</p></li>
<li><p>During the <strong>auditUser</strong> configuration pass, if <code>Mode</code> is not specified, then the computer shows the Sysprep tool&#39;s user interface (UI), prompting the user to select between <strong>Audit</strong> or <strong>OOBE</strong> mode.</p></li>
<li><p>During the <strong>oobeSystem</strong> configuration pass, if <code>Mode</code> is not specified, then <code>Mode</code> defaults to <strong>OOBE</strong>.</p></li>
</ul></td>
</tr>
</tbody>
</table>



## Valid Configuration Passes


auditSystem

auditUser

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [Reseal](microsoft-windows-deployment-reseal.md) | **Mode**

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

[ForceShutdownNow](microsoft-windows-deployment-reseal-forceshutdownnow.md)











