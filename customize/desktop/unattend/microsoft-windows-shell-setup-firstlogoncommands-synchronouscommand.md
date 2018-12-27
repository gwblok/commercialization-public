---
title: SynchronousCommand
description: SynchronousCommand
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1771c6ae-910a-4a48-baa6-713fb22609e0
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# SynchronousCommand

`SynchronousCommand` specifies a single command to run the first time a user logs on to the computer. `FirstLogonCommands` are run after logon but before the user sees the desktop.

If you create a user account that does not include administrative privileges, the following commands may not run:

* If User Account Control is enabled, then when that user logs in for the first time, a dialog box appears, prompting the user with an option to allow an administrator to apply the commands. If the user selects **Cancel**, these commands don’t run.
* If User Account Control is disabled, these commands don’t run.

When you add a script using FirstLogonCommands, it will be triggered on the next boot, even if you boot into audit mode using Ctrl+Shift+F3. If you plan to use audit mode later, add the following setting to skip this script automatically: Microsoft-Windows-Deployment\\Reseal\\[Mode](microsoft-windows-deployment-reseal-mode.md) = Audit.

> [!Note]
> This command now works like [Microsoft-Windows-Shell-Setup-LogonCommands-AsynchronousCommand](microsoft-windows-shell-setup-logoncommands.md). That is, all commands using these unattend settings are now started at the same time, and no longer wait for the previous command to finish.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [CommandLine](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand-commandline.md) | Specifies the path to the command to run. |
| [Description](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand-description.md) | Describes the command to run. |
| [Order](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand-order.md) | Specifies the order in which the command is run. |
| [RequiresUserInput](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand-requiresuserinput.md) | Specifies whether the first logon command launches a dialog box that requires input from the user. This can reduce the delay of the &quot;Preparing Your Desktop&quot; screen. |

> [!Note]
> FirstLogonCommands are not supported in Windows 10 in S mode.

## Valid Configuration Passes

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [FirstLogonCommands](microsoft-windows-shell-setup-firstlogoncommands.md) | **SynchronousCommand**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to set first logon commands.

```XML
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

[FirstLogonCommands](microsoft-windows-shell-setup-firstlogoncommands.md)
