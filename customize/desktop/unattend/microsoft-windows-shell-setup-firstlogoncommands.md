---
title: FirstLogonCommands
description: FirstLogonCommands
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f5506054-3372-45b7-b1e9-7ccab0147157
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 04/04/2018
ms.topic: article


---
# FirstLogonCommands

`FirstLogonCommands` specifies commands to run the first time a user logs on to the computer. These commands run only once. FirstLogonCommands are not supported in Windows 10 in S mode.

> [!Note]
> Windows 10 doesn’t support setting a custom shell prior to OOBE. If you do, you won’t be able to deploy the resulting image.

When a user with administrative privileges logs in for the first time, these commands are run with elevated access privileges.

If you create a user account that does not include administrative privileges, the following commands may not run:

* If User Account Control is enabled, then when that user logs in for the first time, a dialog box appears, prompting the user with an option to allow an administrator to apply the commands. If the user selects **Cancel**, these commands don’t run.
* If User Account Control is disabled, these commands don’t run.

The commands run after logon, prior to showing the desktop.

If the command launches a separate system process, the system process will run independently of the commands. This enables you to create commands that terminate quickly, allowing the user to reach the desktop faster.

Other processes, such as services, are not restricted by `FirstLogonCommands` and will continue to start or to terminate independently.

> [!Note]
> This command now works like [Microsoft-Windows-Shell-Setup-LogonCommands-AsynchronousCommand](microsoft-windows-shell-setup-logoncommands.md): all commands using these unattend settings are now started at the same time, and no longer wait for the previous command to finish.

When you add a script using FirstLogonCommands, it will be triggered on the next boot, even if you boot into audit mode using Ctrl+Shift+F3. If you plan to use audit mode later, add the following setting to skip this script automatically: [Microsoft-Windows-Deployment-Reseal-Mode](microsoft-windows-deployment-reseal-mode.md) = Audit.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [SynchronousCommand](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand.md) | Specifies a command to run the first time a user logs on to the computer, its description, and the order in which it is run. |

## Valid Configuration Passes

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **FirstLogonCommands**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to specify two commands to run after first logon.

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

[RunSynchronous](microsoft-windows-deployment-runsynchronous.md)

[LogonCommands](microsoft-windows-shell-setup-logoncommands.md)

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)
