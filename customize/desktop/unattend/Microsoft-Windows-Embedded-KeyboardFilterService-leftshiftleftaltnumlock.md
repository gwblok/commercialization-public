---
title: LeftShiftLeftAltNumLock
description: Blocks the Left Shift+Left Alt+Num Lock key combination used to open the Mouse Keys dialog box.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7A4535CF-3F32-4624-908D-4B88A84641BE


ms.date: 05/02/2017
ms.topic: article


---

# LeftShiftLeftAltNumLock


Blocks the Left Shift+Left Alt+Num Lock key combination used to open the Mouse Keys dialog box.

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
<td><p>The Left Shift+Left Alt+Num Lock key combination is not blocked.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><em>Blocked</em></p></td>
<td><p>The Left Shift+Left Alt+Num Lock key combination is blocked.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-KeyboardFilterService](microsoft-windows-embedded-keyboardfilterservice.md) | **LeftShiftLeftAltNumLock**

## Valid Configuration Passes


offlineServicing

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-KeyboardFilterService](microsoft-windows-embedded-keyboardfilterservice.md).

## XML example


```
<settings pass="offlineServicing">
    <component name="Microsoft-Windows-Embedded-KeyboardFilterService" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
        <LeftShiftLeftAltNumLock>Blocked</LeftShiftLeftAltNumLock>
    </component>
</settings>t>
</settings>
```

 

 






