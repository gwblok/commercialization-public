---
title: HideAllBootUI
description: Suppresses all Windows UI elements (logo, status indicator, and status message) during startup.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: B2BF86DC-163A-477C-A54B-4AACB5BC4DC3
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HideAllBootUI


Suppresses all Windows UI elements (logo, status indicator, and status message) during startup.

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
<td><p>Do not suppress Windows UI elements during startup.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Suppress Windows UI elements during startup.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-BootExp](microsoft-windows-embedded-bootexp.md) | **HideAllBootUI**

## Valid Configuration Passes


specialize

oobeSystem

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-BootExp](microsoft-windows-embedded-bootexp.md).

## XML example


```
<settings pass="specialize">
    <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <HideAllBootUI>1</HideAllBootUI>
    </component>
</settings>
```

 

 






