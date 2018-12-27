---
title: Action
description: Specifies whether to add, modify, or remove the custom return code configuration from the list.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0A7F8639-C5AA-412B-A785-0EDE456E9AFA
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Action


Specifies whether to add, modify, or remove the custom return code configuration from the list.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AddListItem</p></td>
<td><p>Add a new custom configuration to the list.</p></td>
</tr>
<tr class="even">
<td><p>Modify</p></td>
<td><p>Modify an existing custom configuration.</p></td>
</tr>
<tr class="odd">
<td><p>RemoveListItem</p></td>
<td><p>Remove a custom configuration from the list.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-ShellLauncher](microsoft-windows-embedded-shelllauncher.md) | [UserSettings](microsoft-windows-embedded-shelllauncher-usersettings.md) | [User](microsoft-windows-embedded-shelllauncher-usersettings-user.md) | [CustomReturnCodeAction](microsoft-windows-embedded-shelllauncher-usersettings-user-customreturncodeaction.md) | [CodeAction](microsoft-windows-embedded-shelllauncher-usersettings-user-customreturncodeaction-codeaction.md) | **Action**

## Valid Configuration Passes


oobeSystem

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-ShellLauncher](microsoft-windows-embedded-shelllauncher.md).

## XML example


```
<settings pass="oobeSystem">
    <component name="Microsoft-Windows-Embedded-ShellLauncher" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
        <Shell>testshell.exe</Shell>
        <DefaultReturnCodeAction>1</DefaultReturnCodeAction>
    </component>
</settings>
```

 

 






