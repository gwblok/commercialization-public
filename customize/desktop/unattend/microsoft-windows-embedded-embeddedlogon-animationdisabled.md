---
title: AnimationDisabled
description: Disables the Welcome screen transition animation for custom logon.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ED6949DC-525C-4F9D-8AE0-2C63566F0B45
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# AnimationDisabled


Disables the Welcome screen transition animation for custom logon

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
<td><p>Do not disable the Welcome screen transition animation.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Disable the Welcome screen transition animation.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-EmbeddedLogon](microsoft-windows-embedded-embeddedlogon.md) | **AnimationDisabled**

## Valid Configuration Passes


offlineServicing

specialize

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-EmbeddedLogon](microsoft-windows-embedded-embeddedlogon.md).

## XML example


```
<settings pass="specialize">
    <component name="Microsoft-Windows-Embedded-EmbeddedLogon" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <AnimationDisabled>1</AnimationDisabled>
    </component>
</settings>
```

 

 






