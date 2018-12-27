---
title: DisableKeyboardFilterForAdministrators
description: Disables the keyboard filter for administrators.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: A8A76ADD-704F-4C0B-88EF-70FB9DFFC477


ms.date: 05/02/2017
ms.topic: article


---

# DisableKeyboardFilterForAdministrators


Disables the keyboard filter for administrators.

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
<td><p>The keyboard filter is not disabled for administrators.</p></td>
</tr>
<tr class="even">
<td><p><em>false</em></p></td>
<td><p>The keyboard filter is disabled for administrators.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-KeyboardFilterService](microsoft-windows-embedded-keyboardfilterservice.md) | **DisableKeyboardFilterForAdministrators**

## Valid Configuration Passes


offlineServicing

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-KeyboardFilterService](microsoft-windows-embedded-keyboardfilterservice.md).

## XML example


```
<settings pass="offlineServicing">
    <component name="Microsoft-Windows-Embedded-KeyboardFilterService" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
        <DisableKeyboardFilterForAdministrators>true</DisableKeyboardFilterForAdministrators>
    </component>
</settings>
```

 

 






