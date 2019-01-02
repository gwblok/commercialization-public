---
title: User
description: Use the User settings to specify what custom shell and what default return code action to use for specific users or user groups.
MS-HAID:
- 'p\_unattend.microsoft-windows-embedded-shelllauncher\_user'
- 'p\_unattend.microsoft-windows-embedded-shelllauncher\_usersettings\_user'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: B53B5A1F-6742-435E-8FA7-3EC6902BFC8B
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# User

Use the `User` settings to specify what custom shell and what default return code action to use for specific users or user groups.

## Child elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AccountName](microsoft-windows-embedded-shelllauncher-usersettings-user-accountname.md) | Specifies the user or group account name the custom shell will be used for. |
| [CustomReturnCodeAction](microsoft-windows-embedded-shelllauncher-usersettings-user-customreturncodeaction.md) | Contains the settings to map an exit code from a custom shell to a shell exit action. If the exit code does not match a defined value, Shell Launcher performs the default return action code. |
| [DefaultReturnCodeAction](microsoft-windows-embedded-shelllauncher-usersettings-user-defaultreturncodeaction.md) | Specifies what action to take based on the return code. |
| [Domain](microsoft-windows-embedded-shelllauncher-usersettings-user-domain.md) | Specifies account name's domain. |
| [Key](microsoft-windows-embedded-shelllauncher-usersettings-user-key.md) | Index key for this setting in the setting list. |
| [Shell](microsoft-windows-embedded-shelllauncher-usersettings-user-shell.md) | Specifies the application or executable to use as the default custom shell. |

## Parent Hierarchy

[Microsoft-Windows-Embedded-ShellLauncher](microsoft-windows-embedded-shelllauncher.md) | [UserSettings](microsoft-windows-embedded-shelllauncher-usersettings.md) | **User**

## Applies to

This component applies to the following Windows editions and architectures.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Windows Edition</th>
<th>x86-based processors</th>
<th>x64-based processors</th>
<th>ARM-based processors</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows 10 Enterprise</p></td>
<td><p>x86</p></td>
<td><p>amd64</p></td>
<td><p>Not available</p></td>
</tr>
</tbody>
</table>
