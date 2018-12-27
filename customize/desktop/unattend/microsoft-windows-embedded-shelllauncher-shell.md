---
title: Shell
description: Specifies the application or executable to use as the default custom shell.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: CD72B128-FDE5-49E8-B04A-5E8C7299C8F4
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Shell


Specifies the application or executable to use as the default custom shell.

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
<td><p><em>ExecutableFile</em></p></td>
<td><p>Specifies the name and path, if required, of the executable to use as the default custom shell.</p>
<p>The default value is cmd.exe.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-ShellLauncher](microsoft-windows-embedded-shelllauncher.md) | **Shell**

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

 

 






