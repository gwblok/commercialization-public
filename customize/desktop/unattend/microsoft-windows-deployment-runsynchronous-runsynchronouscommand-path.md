---
title: Path
description: Path
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1ad8938e-24f1-4532-85a3-099c2361c724
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Path


`Path` specifies the path and the name of the command to run. [RunSynchronous](microsoft-windows-deployment-runsynchronous.md) commands run in the user context in the auditUser configuration pass and in the system context in the specialize configuration pass.

**Warning**  
Do not add commands that shut down or reboot the computer; instead, use the setting: Microsoft-Windows-Deployment\\RunSynchronous\\RunSynchronousCommand\\[WillReboot](microsoft-windows-deployment-runsynchronous-runsynchronouscommand-willreboot.md).

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path</em></p></td>
<td><p>Specifies the path and the file name of the command to run synchronously. The path can be a local path or a UNC path. If the path is a UNC path, the <a href="microsoft-windows-deployment-runsynchronous-runsynchronouscommand-credentials.md" data-raw-source="[Credentials](microsoft-windows-deployment-runsynchronous-runsynchronouscommand-credentials.md)">Credentials</a> must be specified. <em>Path</em> is a string with a maximum length of 259 characters.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


auditUser

specialize

## Parent Hierarchy


[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [RunSynchronous](microsoft-windows-deployment-runsynchronous.md) | [RunSynchronousCommand](microsoft-windows-deployment-runsynchronous-runsynchronouscommand.md) | **Path**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

## XML Example


The following XML output shows how to set synchronous commands.

The first command runs an application on the local hard drive. The command includes the environment variable %ProgramFiles%. The second command runs a command from the network.

```
<RunSynchronous>
   <RunSynchronousCommand wcm:action="add">
      <Description>Command1-Local</Description>
      <Order>1</Order>
      <Path>%ProgramFiles%\FabriKam\FabriKam First Run Application.exe</Path>
      <WillReboot>OnRequest</WillReboot>
   </RunSynchronousCommand>
   <RunSynchronousCommand wcm:action="add">
      <Credentials>
         <Domain>MyDomain</Domain>
         <Password>MyPassword</Password>
         <Username>MyUsername</Username>
      </Credentials>
      <Description>Command2-Network</Description>
      <Order>2</Order>
      <Path>\\network\server\share\filename</Path>
      <WillReboot>OnRequest</WillReboot>
   </RunSynchronousCommand>
</RunSynchronous>
```

## Related topics


[RunSynchronousCommand](microsoft-windows-deployment-runsynchronous-runsynchronouscommand.md)

 

 







