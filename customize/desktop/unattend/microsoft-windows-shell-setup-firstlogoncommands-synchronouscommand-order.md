---
title: Order
description: Order
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f1c6b0da-7d2e-47ce-abca-6980b65617b1
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Order


`Order` specifies the order in which the [SynchronousCommand](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand.md) is to be run at first logon.

**Note**  This command now works like Microsoft-Windows-Shell-Setup\\LogonCommands\\[AsynchronousCommand](microsoft-windows-shell-setup-logoncommands.md): all commands using these unattend settings are now started at the same time, and no longer wait for the previous command to finish. 
 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Synchronous_command_order</em></p></td>
<td><p>Specifies the order in which commands are to be run at first logon. <em>Synchronous_command_order</em> is an integer from 1 through 500.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [FirstLogonCommands](microsoft-windows-shell-setup-firstlogoncommands.md) | [SynchronousCommand](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand.md) | **Order**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to set first logon commands.

```
<FirstLogonCommands>
   <SynchronousCommand wcm:action="add">
      <CommandLine>c:\synccommands\command1.exe</CommandLine>
      <Description>Description_of_command1</Description>
      <Order>1</Order>
   </SynchronousCommand>
   <SynchronousCommand wcm:action="add">
      <CommandLine>c:\synccommands\command2.exe</CommandLine>
      <Description>Description_of_command2</Description>
      <Order>2</Order>
   </SynchronousCommand>
</FirstLogonCommands>
```

## Related topics


[SynchronousCommand](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand.md)

[AsynchronousCommand](microsoft-windows-shell-setup-logoncommands-asynchronouscommand.md)

 

 







