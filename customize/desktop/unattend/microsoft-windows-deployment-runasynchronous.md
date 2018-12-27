---
title: RunAsynchronous
description: RunAsynchronous
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 06ac8494-de43-49ac-b1d6-d49451027534
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# RunAsynchronous

`RunAsynchronous` specifies one or more commands to run during the auditUser configuration pass or specialize configuration pass.

To run services or commands that can start at the same time, use asynchronous commands. To run commands that need to finish before other commands can start, use [RunSynchronous](microsoft-windows-deployment-runsynchronous.md) instead.

`RunAsynchronous` commands run in the user context in the auditUser configuration pass and in the system context in the specialize configuration pass.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [RunAsynchronousCommand](microsoft-windows-deployment-runasynchronous-runasynchronouscommand.md) | Specifies the path, the order, and the credentials of the command to run asynchronously. |
 
This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes

auditUser

specialize

## Parent Hierarchy

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | **RunAsynchronous**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

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

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md)

[RunSynchronous](microsoft-windows-deployment-runsynchronous.md)
