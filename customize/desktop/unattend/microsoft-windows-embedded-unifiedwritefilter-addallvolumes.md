---
title: AddAllVolumes
description: Specifies whether to protect all volumes with UWF.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6AEAA423-A55F-45A0-B77F-CEC4EF21C0EE
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# AddAllVolumes

Specifies whether to protect all volumes with UWF.

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
<td><p>False</p></td>
<td><p>Do not protect all volumes.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>Protect all volumes.</p></td>
</tr>
</tbody>
</table>

## Parent Hierarchy

[Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md) | **AddAllVolume**

## Valid Configuration Passes

specialize

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md).

## XML example

```XML
<settings pass="specialize">
    <component name="Microsoft-Windows-Embedded-UnifiedWriteFilter" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
        <AddAllVolumes>True</AddAllVolumes>
    </component>
</settings>
```
