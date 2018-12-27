---
title: DisableBootMenu
description: Disables the F8 and F10 keys during startup to prevent access to the Advanced Startup Options menu.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 793F6DC2-F8B6-45B0-9C08-FBE9B8415449
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisableBootMenu


Disables the F8 and F10 keys during startup to prevent access to the **Advanced Startup Options** menu.

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
<td><p>Do not disable the F8 and F10 keys during startup.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Disable the F8 and F10 keys during startup.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-BootExp](microsoft-windows-embedded-bootexp.md) | **DisableBootMenu**

## Valid Configuration Passes


specialize

oobeSystem

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-BootExp](microsoft-windows-embedded-bootexp.md).

## XML example


```
<settings pass="specialize">
    <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <DisableBootMenu>1</DisableBootMenu>
    </component>
</settings>
```

 

 






