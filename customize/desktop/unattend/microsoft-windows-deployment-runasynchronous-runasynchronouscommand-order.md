---
title: Order
description: Order
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: cf3ff181-2dd9-4c5f-8568-168ff1936a83
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Order


`Order` specifies a unique value for each [RunAsynchronousCommand](microsoft-windows-deployment-runasynchronous-runasynchronouscommand.md).

To run services or commands that can start at the same time, use asynchronous commands. To run commands that need to finish before other commands can start, use [RunSynchronous](microsoft-windows-deployment-runsynchronous.md) instead.

[RunAsynchronous](microsoft-windows-deployment-runasynchronous.md) commands run in the user context in the auditUser configuration pass and in the system context in the specialize configuration pass.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Order</em></p></td>
<td><p>Specifies a unique integer between 1 and 500.</p>
<div class="alert">
<strong>Important</strong><br/><p>Unlike synchronous commands, the computer does not wait for one asynchronous command to finish before it starts the next command.</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## Valid Configuration Passes


auditUser

specialize

## Parent Hierarchy


[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [RunAsynchronous](microsoft-windows-deployment-runasynchronous.md) | [RunAsynchronousCommand](microsoft-windows-deployment-runasynchronous-runasynchronouscommand.md) | **Order**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

## XML Example


The following XML output shows how to set asynchronous commands.

```
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


[RunAsynchronousCommand](microsoft-windows-deployment-runasynchronous-runasynchronouscommand.md)











