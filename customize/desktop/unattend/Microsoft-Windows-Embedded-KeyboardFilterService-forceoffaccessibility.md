---
title: ForceOffAccessibility
description: Disables all Ease of Access features and prevents users from enabling them.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 23DB4C3C-8FD0-435C-BE4E-36742F82E68C


ms.date: 05/02/2017
ms.topic: article


---

# ForceOffAccessibility


Disables all Ease of Access features and prevents users from enabling them.

## Type


Boolean

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
<td><p><em>true</em></p></td>
<td><p>The ForceOffAccessibility key is blocked.</p></td>
</tr>
<tr class="even">
<td><p><em>false</em></p></td>
<td><p>The ForceOffAccessibility key is not blocked.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-KeyboardFilterService](microsoft-windows-embedded-keyboardfilterservice.md) | **ForceOffAccessibility**

## Valid Configuration Passes


offlineServicing

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-KeyboardFilterService](microsoft-windows-embedded-keyboardfilterservice.md).

## XML example


```
<settings pass="offlineServicing">
    <component name="Microsoft-Windows-Embedded-KeyboardFilterService" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
        <ForceOffAccessibility>true</ForceOffAccessibility>
    </component>
</settings>
```

 

 






