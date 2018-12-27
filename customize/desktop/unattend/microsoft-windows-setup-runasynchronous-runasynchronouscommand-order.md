---
title: Order
description: Order
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 416c4f09-43ff-4efd-93c9-6a6f8500c097
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Order


`Order` specifies a unique value for each AsynchronousCommand.

To run services or commands that can start at the same time, use asynchronous commands. To run commands that need to finish before other commands can start, use [RunSynchronous](microsoft-windows-setup-runsynchronous.md) commands instead.

All [RunAsynchronous](microsoft-windows-setup-runasynchronous.md) commands run in the system context.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Asynchronous_command_order</em></p></td>
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


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [RunAsynchronous](microsoft-windows-setup-runasynchronous.md) | [RunAsynchronousCommand](microsoft-windows-setup-runasynchronous-runasynchronouscommand.md) | **Order**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to configure asynchronous commands to run.

```
<RunAsynchronous>
   <RunAsynchronousCommand>
      <Order>1</Order>
      <Path>\\MyNetworkShare\MyApplication.exe</Path>
      <Description>DescriptionOfMyApplication</Description>
      <Credentials>
         <Domain>FabrikamDomain</Domain>
         <UserName>MyUserName</UserName>
         <Password>MyPassword</Password>
      </Credentials>
   </RunAsynchronousCommand>
   <RunAsynchronousCommand>
      <Order>2</Order>
      <Path>C:\AnotherApplication.exe</Path>
      <Description>DescriptionOfMyApplication</Description>
   </RunAsynchronousCommand>
</RunAsynchronous>
```

## Related topics


[RunAsynchronousCommand](microsoft-windows-setup-runasynchronous-runasynchronouscommand.md)

[RunSynchronous](microsoft-windows-setup-runsynchronous.md)











