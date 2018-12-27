---
title: LogonCount
description: LogonCount
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: da3e5987-4834-4bca-a543-8987724eae88
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 12/11/2017
ms.topic: article


---
# LogonCount

`LogonCount` specifies the number of times that you can log on to the computer by using `AutoLogon`. This value decrements each time you log on to the computer. You must restart the computer to reset the value of `LogonCount`. `LogonCount` must be specified if [AutoLogon](microsoft-windows-shell-setup-autologon.md) is used.

After the specified number of automated logon actions has occurred, you must manually log onto the computer.

If the built-in administrator account is used, the account is still active. For more information about the built-in administrator account, see the [How to Enable and Disable the Built-in Administrator Account](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/enable-and-disable-the-built-in-administrator-account) topic in the Windows Assessment and Deployment Kit (Windows ADK) Technical Reference.

## Values

| Value             | Description                       |
|:------------------|:----------------------------------|
| *Logon_count*     | The number of times you can log on to the computer by using `AutoLogon`. *Logon_count* is an integer.            |

### LogonCount known issue

Please note that there is a known issue which causes Windows to add 1 to the `LogonCount` value, if that value is greater than 0. When setting `LogonCount`, enter a number that is one fewer than the number of automated logons you desire. For example, to facilitate 2 automated logons, set `LogonCount` to 1.

If `LogonCount` is 0, Windows correctly interprets this and will not perform any automated logons. Because of this known issue, the `LogonCount` Unattend setting cannot be used to allow exactly one automated logon. To work around this known issue, take the following steps:

1. Set `LogonCount` to 1.
2. Add a new command under the `Microsoft-Windows-Shell-Setup/FirstLogonCommands/SynchronousCommand` Unattend setting for the oobeSystem pass:

   `reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon" /v AutoLogonCount /t REG_DWORD /d 0 /f`

See [FirstLogonCommands](microsoft-windows-shell-setup-firstlogoncommands.md) in the Unattended Setup Reference to learn more about this setting.

## Valid Configuration Passes

* auditSystem
* oobeSystem
* specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [AutoLogon](microsoft-windows-shell-setup-autologon.md) | **LogonCount**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md). This setting is not configured in a Nano Server image.

## XML Example

The following XML output shows how to set `AutoLogon` so that you can log onto the computer using the built-in administrator account.

```XML
<AutoLogon>
   <Password>
      <Value>MyPassword</Value>
      <PlainText>true</PlainText>
   </Password>
   <Enabled>true</Enabled>
   <LogonCount>2</LogonCount>
   <Username>Administrator</Username>
</AutoLogon>
```

## Related topics

[How to Enable and Disable the Built-in Administrator Account](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/enable-and-disable-the-built-in-administrator-account)
