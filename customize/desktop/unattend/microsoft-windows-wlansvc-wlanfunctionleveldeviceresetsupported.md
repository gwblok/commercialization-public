---
title: WLANFunctionLevelDeviceResetSupported
description: Specifies whether the device supports functional level device reset (FLDR). The FLDR feature in the OS checks this system capability exclusively to determine if it can run.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3D044025-F0B6-4546-9DF9-CBFB09DA7A97
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# WLANFunctionLevelDeviceResetSupported

> [!Important]
> This setting is deprecated in Windows 10, version 1803.


Specifies whether the device supports functional level device reset (FLDR). The FLDR feature in the OS checks this system capability exclusively to determine if it can run.

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
<td><p>Disables functional level device reset.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Enables functional level device reset.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Wlansvc](microsoft-windows-wlansvc.md) | **WLANFunctionLevelDeviceResetSupported**

## Valid Configuration Passes


offlineServicing

specialize

oobeSystem

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Wlansvc](microsoft-windows-wlansvc.md).

## Related topics


[Microsoft-Windows-Wlansvc](microsoft-windows-wlansvc.md)

 

 







