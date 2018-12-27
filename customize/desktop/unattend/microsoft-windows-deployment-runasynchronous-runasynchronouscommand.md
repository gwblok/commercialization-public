---
title: RunAsynchronousCommand
description: RunAsynchronousCommand
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: cef754b4-9101-4d74-a036-66c4ed395f83
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# RunAsynchronousCommand

`RunAsynchronousCommand` specifies a single command to run during the auditUser Configuration Pass or specialize Configuration Pass.

To run services or commands that can start at the same time, use asynchronous commands. To run commands that need to finish before other commands can start, use [RunSynchronousCommand](microsoft-windows-deployment-runsynchronous-runsynchronouscommand.md) instead.

`RunAsynchronous` commands run in the user context in the auditUser Configuration Pass and in the system context in the specialize Configuration Pass.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Credentials](microsoft-windows-deployment-runasynchronous-runasynchronouscommand-credentials.md) | Specifies the credentials to use when accessing paths. |
| [Description](microsoft-windows-deployment-runasynchronous-runasynchronouscommand-description.md) | Specifies a description of the command to execute. |
| [Order](microsoft-windows-deployment-runasynchronous-runasynchronouscommand-order.md) | Specifies a unique value for each command.<br/>
**Important**: The computer does not wait for one command to finish before it starts the next one. |
| [Path](microsoft-windows-deployment-runasynchronous-runasynchronouscommand-path.md) | Specifies the path to the command to execute. |

## Valid Configuration Passes

auditUser

specialize

## Parent Hierarchy

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [RunAsynchronous](microsoft-windows-deployment-runasynchronous.md) | **RunAsynchronousCommand**

## Applies To

For the list of the supported Windows editions and architectures this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

## XML Example

The following XML output shows how to set asynchronous commands.

```XML
<RunAsynchronous>
   <RunAsynchronousCommand wcm:action="add">
      <Credentials>
         <Domain>MyDomain</Domain>
         <Password>MyPassword</Password>
         <Username>MyUsername</Username>
      </Credentials>
      <Description>AsynchCommand1</Description>
      <Order>1</Order>
      <Path>\\network\server\share\filename</Path>
   </RunAsynchronousCommand>
   <RunAsynchronousCommand wcm:action="add">
      <Credentials>
         <Domain>MyDomain</Domain>
         <Password>MyPassword</Password>
         <Username>MyUsername</Username>
      </Credentials>
      <Description>AsynchCommand2</Description>
      <Order>2</Order>
      <Path>\\network\server\share\filename</Path>
   </RunAsynchronousCommand>
</RunAsynchronous>
```

## Related topics

[RunAsynchronous](microsoft-windows-deployment-runasynchronous.md)

[RunSynchronousCommand](microsoft-windows-deployment-runsynchronous-runsynchronouscommand.md)
