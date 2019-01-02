---
title: EnableVirtualizationBasedSecurity
description: Use to enable virtualization-based security.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 32C940A8-7BF8-4541-97BB-27F2695DE9B6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# EnableVirtualizationBasedSecurity

Use to enable virtualization-based security.

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
<td><p>Disables virtualization-based security.</p>
<p>This is the default OS value.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Enables virtualization-based security.</p></td>
</tr>
</tbody>
</table>

If this setting is set to 0 or is not present, the system doesn't read other values and VSM is not enforced. In this case, existing BCD settings are used.

## Parent Hierarchy

[Microsoft-Windows-DeviceGuard-Unattend](microsoft-windows-deviceguard-unattend.md) | **EnableVirtualizationBasedSecurity**

## Valid Configuration Passes

offlineServicing

## Applies To

Windows 10 Enterprise

Windows Server 2016

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-DeviceGuard-Unattend](microsoft-windows-deviceguard-unattend.md).
