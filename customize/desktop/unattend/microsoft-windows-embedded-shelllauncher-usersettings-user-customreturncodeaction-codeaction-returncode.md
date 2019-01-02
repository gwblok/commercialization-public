---
title: ReturnCode
description: Specifies the custom return code to map to the indicated shell exist code.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 18081ADE-18AF-414B-B1E8-2587110EA220
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ReturnCode


Specifies the custom return code to map to the indicated shell exist code.

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
<td><p><em>CustomReturnCode</em></p></td>
<td><p>Specifies the return code to map to the indicated shell exit code.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-ShellLauncher](microsoft-windows-embedded-shelllauncher.md) | [UserSettings](microsoft-windows-embedded-shelllauncher-usersettings.md) | [User](microsoft-windows-embedded-shelllauncher-usersettings-user.md) | [CustomReturnCodeAction](microsoft-windows-embedded-shelllauncher-usersettings-user-customreturncodeaction.md) | [CodeAction](microsoft-windows-embedded-shelllauncher-usersettings-user-customreturncodeaction-codeaction.md) | **ReturnCode**

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

 

 






