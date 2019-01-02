---
title: RequiresUserInput
description: RequiresUserInput
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7296b2b6-9d8d-4d90-b557-7bcf7544574f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# RequiresUserInput


The `RequiresUserInput` setting is not used.

**Note**  
Unlike synchronous commands, asynchronous commands may start and finish in any order. They cannot delay the appearance of the Windows desktop, even if the asynchronous command requires user input. If an asynchronous command requires user input, the end user will see the input window after the desktop appears. For information about synchronous commands, see [SynchronousCommand](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand.md).

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>This setting is not used.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>This setting is not used.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [LogonCommands](microsoft-windows-shell-setup-logoncommands.md) | [AsynchronousCommand](microsoft-windows-shell-setup-logoncommands-asynchronouscommand.md) | **RequiresUserInput**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows examples of how to set two logon commands. The `RequiresUserInput` setting has no effect for either of the commands.

```
<LogonCommands>
  <AsynchronousCommand wcm:action="add">
    <CommandLine>c:\asynccommands\command1.exe</CommandLine>
    <Description>Description_of_command1</Description>
    <Order>1</Order>
    <RequiresUserInput>true</RequiresUserInput>
  </AsynchronousCommand>
  <AsynchronousCommand wcm:action="add">
    <CommandLine>c:\asynccommands\command2.exe</CommandLine>
    <Description>Description_of_command2</Description>
    <Order>2</Order>
    <RequiresUserInput>false</RequiresUserInput>
  </AsynchronousCommand>
</LogonCommands>
```

## Related topics


[AsynchronousCommand](microsoft-windows-shell-setup-logoncommands-asynchronouscommand.md)

[RequiresUserInput](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand-requiresuserinput.md)

 

 







