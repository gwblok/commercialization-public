---
title: RequiresUserInput
description: RequiresUserInput
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b086d8e4-8b34-4493-bc81-215bd758bd9b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# RequiresUserInput


`RequiresUserInput` specifies whether the first logon command launches a dialog that requires input from the user.

After the Windows Out of Box Experience (OOBE), the "Preparing Your Desktop" screen appears. This screen prevents users from interacting with the first logon commands, and is intended to efficiently run the logon commands that do not require user input.

If a first logon command requires user input, end users may be forced to wait up to two minutes before they can see the desktop. After this delay, they can interact with the user interface that requires their input. You can use the `RequiresUserInput` setting to reduce this delay.

**Note**  
-   If the command that requires user input is not dependent on other commands, consider using an asynchronous command instead. Unlike synchronous commands, asynchronous commands may start and finish in any order. Asynchronous commands cannot delay the appearance of the Windows desktop, even if the asynchronous command requires user input. If an asynchronous command requires user input, the end user will see the input window after the desktop appears. For information about asynchronous commands, see [AsynchronousCommand](microsoft-windows-shell-setup-logoncommands-asynchronouscommand.md).

-   If you have multiple first logon commands, we recommend that you set the command that requires user input last in the order of first logon commands. This will help to prevent users from interfering with the other first logon commands.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the first logon command requires user input.</p>
<p>The &quot;Preparing Your Desktop&quot; screen is removed, allowing users to reach the desktop more quickly and provide input.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the first logon command does not require user input.</p>
<p>The desktop does not appear until first logon command is complete, or until two minutes pass.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [FirstLogonCommands](microsoft-windows-shell-setup-firstlogoncommands.md) | [SynchronousCommand](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand.md) | **RequiresUserInput**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to specify that one of the first logon commands requires user input.

```
<FirstLogonCommands>
   <SynchronousCommand wcm:action="add">
      <CommandLine>c:\synccommands\command1.exe</CommandLine>
      <Description>Description of command 1</Description>
      <Order>1</Order>
   </SynchronousCommand>
   <SynchronousCommand wcm:action="add">
      <CommandLine>c:\synccommands\command2.exe</CommandLine>
      <Description>Description of command 2 - This command requires user input</Description>
      <Order>2</Order>
      <RequiresUserInput>true</RequiresUserInput>
   </SynchronousCommand>
</FirstLogonCommands>
```

## Related topics


[SynchronousCommand](microsoft-windows-shell-setup-firstlogoncommands-synchronouscommand.md)

[AsynchronousCommand](microsoft-windows-shell-setup-logoncommands-asynchronouscommand.md)

 

 







