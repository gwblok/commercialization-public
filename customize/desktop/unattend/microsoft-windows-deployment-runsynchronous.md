---
title: RunSynchronous
description: RunSynchronous
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5a20d90e-f23f-4227-a974-377a114d8369
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# RunSynchronous

`RunSynchronous` specifies one or more commands to run in series during the auditUser configuration pass or specialize configuration pass. Synchronous commands are executed in the order specified in the unattended installation answer file, and each command must finish before the next command runs.

`RunSynchronous` commands run in the user context in the auditUser configuration pass and in the system context in the specialize configuration pass.

To start a command that needs to finish before other commands can start, use synchronous commands. To run services or commands that can start at the same time, use [RunAsynchronous](microsoft-windows-deployment-runasynchronous.md) instead.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [RunSynchronousCommand](microsoft-windows-deployment-runsynchronous-runsynchronouscommand.md) | Specifies the path, the order, and the credentials of the command to run synchronously. |

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes

auditUser

specialize

## Parent Hierarchy

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | **RunSynchronous**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

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

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md)
