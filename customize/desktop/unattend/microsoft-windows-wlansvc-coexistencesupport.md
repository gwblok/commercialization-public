---
title: CoexistenceSupport
description: Specifies the type of co-existence that's supported on the device Both - Both Wi-Fi and Bluetooth work at the same performance level during co-existence.Wi-Fi reduced - On a 2X2 system, Wi-Fi performance is reduced to 1X1 level.Bluetooth centered - When co-existing, Bluetooth has priority and restricts Wi-Fi performance.One - Either Wi-Fi or Bluetooth will stop working.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 628ED36C-9B25-4450-AC96-C66FC2F0B901
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# CoexistenceSupport


Specifies the type of co-existence that's supported on the device:

-   **Both** - Both Wi-Fi and Bluetooth work at the same performance level during co-existence.
-   **Wi-Fi reduced** - On a 2X2 system, Wi-Fi performance is reduced to 1X1 level.
-   **Bluetooth centered** - When co-existing, Bluetooth has priority and restricts Wi-Fi performance.
-   **One** - Either Wi-Fi or Bluetooth will stop working.

This setting is used for telemetry only. There is no OS action associated with this setting.

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
<td><p>1</p></td>
<td><strong>Both</strong></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><strong>Wi-Fi reduced</strong></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><strong>Bluetooth centered</strong></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><strong>One</strong></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Wlansvc](microsoft-windows-wlansvc.md) | **CoexistenceSupport**

## Valid Configuration Passes


offlineServicing

specialize

oobeSystem

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Wlansvc](microsoft-windows-wlansvc.md).

## Related topics


[Microsoft-Windows-Wlansvc](microsoft-windows-wlansvc.md)

 

 







