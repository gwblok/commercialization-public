---
title: CommandLine
description: CommandLine
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 09271df1-5146-463b-b0e2-2aed8b6cc7ce
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# CommandLine


`CommandLine` specifies the path to the [SynchronousCommand](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand.md) to be run at first logon.

If you create a user account that does not include administrative privileges, the following commands may not be executed:

-   If User Account Control is enabled, then when that user logs in for the first time, a dialog box appears, prompting the user with an option to allow an administrator to apply the commands. If the user selects **Cancel**, these commands are not executed.

-   If User Account Control is disabled, these commands are not executed.

When you add a script using FirstLogonCommands, it will be triggered on the next boot, even if you boot into audit mode using Ctrl+Shift+F3. If you plan to use audit mode later, add the following setting to skip this script automatically: Microsoft-Windows-Deployment\\Reseal\\[Mode](microsoft-windows-deployment-reseal-mode.md) = Audit.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path_to_command</em></p></td>
<td><p>Specifies the path to the command to be run at first logon. <em>Path_to_command</em> is a string with a maximum length of 1024 characters.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [FirstLogonCommands](microsoft-windows-shell-setup-firstlogoncommands.md) | [SynchronousCommand](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand.md) | **CommandLine**

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

 

 







