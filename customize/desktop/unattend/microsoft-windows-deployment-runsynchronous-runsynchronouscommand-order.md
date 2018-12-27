---
title: Order
description: Order
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 168ada63-42bf-4be3-9093-e22fa2e52152
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Order


`Order` specifies the order in which to execute the synchronous command.

Synchronous commands start in the order specified in the unattended installation answer file, and each command must finish before the next command starts.

To start a command that needs to finish before other commands can start, use synchronous commands. To run services or commands that can start at the same time, use [RunAsynchronous](microsoft-windows-deployment-runasynchronous.md) instead.

[RunSynchronous](microsoft-windows-deployment-runsynchronous.md) commands run in the user context in the auditUser configuration pass and in the system context in the specialize configuration pass.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Order</em></p></td>
<td><p>Specifies the order in which synchronous commands are to be executed. <em>Order</em> is an integer between 1 and 500.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


auditUser

specialize

## Parent Hierarchy


[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [RunSynchronous](microsoft-windows-deployment-runsynchronous.md) | [RunSynchronousCommand](microsoft-windows-deployment-runsynchronous-runsynchronouscommand.md) | **Order**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

## XML Example


The following XML output shows how to set synchronous commands.

```
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


[RunSynchronousCommand](microsoft-windows-deployment-runsynchronous-runsynchronouscommand.md)

 

 







