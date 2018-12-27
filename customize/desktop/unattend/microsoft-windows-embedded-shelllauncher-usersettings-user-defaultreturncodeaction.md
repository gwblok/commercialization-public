---
title: DefaultReturnCodeAction
description: Specifies what action to take based on the return code.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 47111F61-7258-4046-9D48-1B6D153EAF6F
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DefaultReturnCodeAction


Specifies what action to take based on the return code.

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
<td><p>0</p></td>
<td><p>Restart the shell.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Restart the device.</p></td>
</tr>
<tr class="odd">
<td><p>2</p></td>
<td><p>Shut down the device.</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>Do nothing.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-ShellLauncher](microsoft-windows-embedded-shelllauncher.md) | [UserSettings](microsoft-windows-embedded-shelllauncher-usersettings.md) | [User](microsoft-windows-embedded-shelllauncher-usersettings-user.md) | **DefaultCodeReturnCodeAction**

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

 

 






