---
title: Description
description: Description
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ef75ad0a-573b-4533-852c-80b771370d6d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Description


`Description` gives a brief description of the [SynchronousCommand](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand.md) to be run at first logon.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Command_description</em></p></td>
<td><p>Describes the command to be run at first logon. <em>Command_description</em> is a string with a maximum length of 256 characters.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [FirstLogonCommands](microsoft-windows-shell-setup-firstlogoncommands.md) | [SynchronousCommand](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand.md) | **Description**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

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

 

 







