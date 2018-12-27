---
title: Key
description: Index key for this setting in the setting list.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1C9BC1E2-9680-499B-92FD-01FFD3846DE2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Key


Index key for this setting in the setting list.

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
<td><p><em>IntegerKey</em></p></td>
<td><p>Specifies the unique key of this user setting in the list.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-ShellLauncher](microsoft-windows-embedded-shelllauncher.md) | [UserSettings](microsoft-windows-embedded-shelllauncher-usersettings.md) | [User](microsoft-windows-embedded-shelllauncher-usersettings-user.md) | **Key**

## Valid Configuration Passes


oobeSystem

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-ShellLauncher](microsoft-windows-embedded-shelllauncher.md).

## XML example


```
<settings pass="oobeSystem">
    <component name="Microsoft-Windows-Embedded-ShellLauncher" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
        <UserSettings>
            <User wcm:action="add">
                <AccountName>Tester1</AccountName>
                <DefaultReturnCodeAction>0</DefaultReturnCodeAction>
                <Domain>TestDomain</Domain>
                <Key>1</Key>
                <Shell>cmd.exe</Shell>
            </User>
    </component>
</settings>
```

 

 






