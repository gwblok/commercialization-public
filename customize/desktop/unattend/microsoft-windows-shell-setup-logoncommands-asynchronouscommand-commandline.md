---
title: CommandLine
description: CommandLine
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 70bf0836-459e-4e78-bcca-2a9a8a62face
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# CommandLine


`CommandLine` specifies the path to the [AsynchronousCommand](microsoft-windows-shell-setup-logoncommands-asynchronouscommand.md) to be run.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path_to_command_line</em></p></td>
<td><p>Specifies the path to the command. <em>Path_to_command_line</em> is a string with a maximum length of 1024 characters.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [LogonCommands](microsoft-windows-shell-setup-logoncommands.md) | [AsynchronousCommand](microsoft-windows-shell-setup-logoncommands-asynchronouscommand.md) | **CommandLine**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to set logon commands.

```
<LogonCommands>
   <AsynchronousCommand wcm:action="add">
      <CommandLine>c:\asynccommands\command1.exe</CommandLine>
      <Description>Description_of_command1</Description>
      <Order>1</Order>
   </AsynchronousCommand>
   <AsynchronousCommand wcm:action="add">
      <CommandLine>c:\asynccommands\command2.exe</CommandLine>
      <Description>Description_of_command2</Description>
      <Order>2</Order>
   </AsynchronousCommand>
</LogonCommands>
```

## Related topics


[AsynchronousCommand](microsoft-windows-shell-setup-logoncommands-asynchronouscommand.md)

 

 







