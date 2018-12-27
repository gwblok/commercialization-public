---
title: DisplayDisabled
description: Configures the device to display a blank screen when the OS encounters an error that it cannot recover from.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2C81F251-4BA5-4FB0-A81A-C2DC3DFC3B33
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisplayDisabled


Configures the device to display a blank screen when the OS encounters an error that it cannot recover from.

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
<td><p>Do not display a blank screen on error.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Display a blank screen on error.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-BootExp](microsoft-windows-embedded-bootexp.md) | **DisplayDisabled**

## Valid Configuration Passes


specialize

oobeSystem

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-BootExp](microsoft-windows-embedded-bootexp.md).

## XML example


```
<settings pass="specialize">
    <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <DisplayDisabled>1</DisplayDisabled>
    </component>
</settings>
```

 

 






