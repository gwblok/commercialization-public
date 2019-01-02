---
title: WindowsP
description: Blocks the Windows logo key+P key combination used to cycle through Presentation Mode. Also blocks the Windows logo key+Shift+P and Windows logo key+Ctrl+P key combinations.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: C0594FA6-6AB2-4E50-AD79-A08E5B8E2837


ms.date: 05/02/2017
ms.topic: article


---

# WindowsP


Blocks the Windows logo key+P key combination used to cycle through Presentation Mode. Also blocks the Windows logo key+Shift+P and Windows logo key+Ctrl+P key combinations.

## Type


String

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
<td><p><em>Allowed</em></p></td>
<td><p>The Windows logo key+P, Windows logo key+Shift+P, and Windows logo key+Ctrl+P key combination are not blocked.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><em>Blocked</em></p></td>
<td><p>The Windows logo key+P, Windows logo key+Shift+P, and Windows logo key+Ctrl+P key combination are blocked.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-KeyboardFilterService](microsoft-windows-embedded-keyboardfilterservice.md) | **WindowsP**

## Valid Configuration Passes


offlineServicing

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-KeyboardFilterService](microsoft-windows-embedded-keyboardfilterservice.md).

## XML example


```
<settings pass="offlineServicing">
    <component name="Microsoft-Windows-Embedded-KeyboardFilterService" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
        <WindowsP>Blocked</WindowsP>
    </component>
</settings>
```

 

 






