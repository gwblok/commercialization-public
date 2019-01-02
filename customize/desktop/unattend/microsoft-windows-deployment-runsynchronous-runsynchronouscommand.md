---
title: RunSynchronousCommand
description: RunSynchronousCommand
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3a4c07a3-b657-4dbc-a6dc-32ad33f447fb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# RunSynchronousCommand

`RunSynchronousCommand` specifies a single command to run during the specified configuration pass.

To start a command that needs to finish before other commands can start, use synchronous commands. To run services or commands that can start at the same time, use [RunAsynchronous](microsoft-windows-deployment-runasynchronous.md) instead.

[RunSynchronous](microsoft-windows-deployment-runsynchronous.md) commands always run before commands in the same pass. `RunSynchronous` commands run in the user context in the auditUser configuration pass configuration pass and in the system context in the specialize configuration pass.

> [!Warning]
> Do not add commands that shut down or reboot the computer; instead, use the setting: Microsoft-Windows-Deployment\\RunSynchronous\\RunSynchronousCommand\\[WillReboot](microsoft-windows-deployment-runsynchronous-runsynchronouscommand-willreboot.md).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Credentials](microsoft-windows-deployment-runsynchronous-runsynchronouscommand-credentials.md) | Specifies the credentials to use when accessing paths. |
| [Description](microsoft-windows-deployment-runsynchronous-runsynchronouscommand-description.md) | Specifies a description of the command to run. |
| [Order](microsoft-windows-deployment-runsynchronous-runsynchronouscommand-order.md) | Specifies the order of the command to run. |
| [Path](microsoft-windows-deployment-runsynchronous-runsynchronouscommand-path.md) | Specifies the path to the command to run. |
| [WillReboot](microsoft-windows-deployment-runsynchronous-runsynchronouscommand-willreboot.md) | Specifies in what circumstances to restart the computer after running a synchronous command. |

## Valid Configuration Passes

auditUser

specialize

## Parent Hierarchy

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [RunSynchronous](microsoft-windows-deployment-runsynchronous.md) | **RunSynchronousCommand**

## Applies To

For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

## XML Example

The following XML output shows how to set synchronous commands.

```XML
<RunSynchronous>
   <RunSynchronousCommand wcm:action="add">
      <Credentials>
         <Domain>MyDomain</Domain>
         <Password>MyPassword</Password>
         <Username>MyUsername</Username>
      </Credentials>
      <Description>MySynchCommand1</Description>
      <Order>1</Order>
      <Path>\\network\server\share\filename</Path>
      <WillReboot>OnRequest</WillReboot>
   </RunSynchronousCommand>
   <RunSynchronousCommand wcm:action="add">
      <Credentials>
         <Domain>MyDomain</Domain>
         <Password>MyPassword</Password>
         <Username>MyUsername</Username>
      </Credentials>
      <Description>MySynchCommand2</Description>
      <Order>2</Order>
      <Path>\\network\server\share\filename</Path>
      <WillReboot>OnRequest</WillReboot>
   </RunSynchronousCommand>
</RunSynchronous>
```

## Related topics

[RunSynchronous](microsoft-windows-deployment-runsynchronous.md)

[RunAsynchronous](microsoft-windows-deployment-runasynchronous.md)
