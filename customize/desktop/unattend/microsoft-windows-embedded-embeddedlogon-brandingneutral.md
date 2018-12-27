---
title: BrandingNeutral
description: Specifies which UI elements display on the Welcome screen.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6B2FE91F-030A-4A37-8F34-E26F92E3464B
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# BrandingNeutral


Specifies which UI elements display on the Welcome screen.

## Values


The following table shows the possible values. You can combine these values using bitwise exclusive-OR logic to disable multiple Welcome screen UI elements.

The default value is 17, which disables all Welcome screen UI elements and the **Switch user** button.

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
<td><p>1</p></td>
<td><p>Disables all Welcome screen UI elements.</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>Disables the <strong>Power</strong> button.</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>Disables the <strong>Language</strong> button.</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>Disables the <strong>Ease of access</strong> button.</p></td>
</tr>
<tr class="odd">
<td><p>16</p></td>
<td><p>Disables the <strong>Switch user</strong> button.</p></td>
</tr>
<tr class="even">
<td><p>32</p></td>
<td><p>Disables the blocked shutdown resolver (BSDR) screen so that restarting or shutting down the system causes the OS to immediately force close any applications that are blocking system shut down. No UI is displayed and users are not given a chance to cancel the shutdown process. This can result in a loss of data if any open applications have unsaved data.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-EmbeddedLogon](microsoft-windows-embedded-embeddedlogon.md) | **BrandingNeutral**

## Valid Configuration Passes


offlineServicing

specialize

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-EmbeddedLogon](microsoft-windows-embedded-embeddedlogon.md).

## XML example


```
<settings pass="specialize">
    <component name="Microsoft-Windows-Embedded-EmbeddedLogon" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <BrandingNeutral>17</BrandingNeutral>
    </component>
</settings>
```

 

 






