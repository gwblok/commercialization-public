---
title: WLANPlatformLevelDeviceResetSupported
description: Specifies whether the device supports platform level device reset (PLDR). The PLDR feature in the OS checks this system capability exclusively to determine if it can run.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: D370826E-FC8D-4A48-A04A-4ACE17D516D2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# WLANPlatformLevelDeviceResetSupported

> [!Important]
> This setting is deprecated in Windows 10, version 1803.


Specifies whether the device supports platform level device reset (PLDR). The PLDR feature in the OS checks this system capability exclusively to determine if it can run.

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
<td><p>Disables platform level device reset.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Enables platform level device reset.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Wlansvc](microsoft-windows-wlansvc.md) | **WLANPlatformLevelDeviceResetSupported**

## Valid Configuration Passes


offlineServicing

specialize

oobeSystem

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Wlansvc](microsoft-windows-wlansvc.md).

## Related topics


[Microsoft-Windows-Wlansvc](microsoft-windows-wlansvc.md)

 

 







