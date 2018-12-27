---
title: Path
description: Path
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3aa12be4-75f9-49a5-8d60-2f25d0f7be33
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Path


`Path` specifies the path and the name of the command to execute. [RunAsynchronous](microsoft-windows-deployment-runasynchronous.md) commands run in the user context in the auditUser configuration pass and in the system context in the specialize configuration pass.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path</em></p></td>
<td><p>Specifies the path and the file name of the command to execute asynchronously. The path can be a local path or a Universal Naming Convention (UNC) path. If the path is a UNC path, the <a href="microsoft-windows-deployment-runasynchronous-runasynchronouscommand-credentials.md" data-raw-source="[Credentials](microsoft-windows-deployment-runasynchronous-runasynchronouscommand-credentials.md)">Credentials</a> setting must be specified.</p>
<p><em>Path</em> is a string with a maximum length of 259 characters.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


auditUser

specialize

## Parent Hierarchy


[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [RunAsynchronous](microsoft-windows-deployment-runasynchronous.md) | [RunAsynchronousCommand](microsoft-windows-deployment-runasynchronous-runasynchronouscommand.md) | **Path**

## Applies To


For a list of the supported Windows editions and architectures this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

## XML Example


The following XML output shows how to set asynchronous commands.

The first command runs an application on the local hard drive. The command includes the environment variable %ProgramFiles%. The second command runs a command from the network.

```
<RunAsynchronous>
   <RunAsynchronousCommand wcm:action="add">
      <Description>AsynchCommand1</Description>
      <Order>1</Order>
      <Path>%ProgramFiles%\FabriKam\FabriKam First Run Application.exe</Path>
   </RunAsynchronousCommand>
   <RunAsynchronousCommand wcm:action="add">
      <Credentials>
         <Domain>MyDomain</Domain>
         <Password>MyPassword</Password>
         <Username>MyUsername</Username>
      </Credentials>
      <Description>SynchCommand2-FromNetwork</Description>
      <Order>2</Order>
      <Path>\\network\server\share\filename</Path>
   </RunAsynchronousCommand>
</RunAsynchronous>
```

## Related topics


[RunAsynchronousCommand](microsoft-windows-deployment-runasynchronous-runasynchronouscommand.md)

 

 







