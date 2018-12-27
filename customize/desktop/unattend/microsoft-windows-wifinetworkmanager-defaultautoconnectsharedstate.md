---
title: DefaultAutoConnectSharedState
description: If enabled, the OOBE Wi-Fi Sense checkbox to share networks with contacts will be checked.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: C1D49D34-AD37-47C7-A358-C08ED5217EF8
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DefaultAutoConnectSharedState

**This setting has been deprecated**. The information about this deprecated setting is provided for reference only. The Wi-Fi Sense credential sharing feature has been removed.

**Important**  
All Wi-Fi sense default settings must be on (or set to 1) unless Microsoft executive approval has been granted for specific mobile operator requests, or for countries listed as exempt.

 

## Values


Set the value of `DefaultAutoConnectSharedState` to one of the following values:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Sets the checkbox for <strong>Allow me to exchange Wi-Fi network access with my contacts</strong> during device OOBE.</p>
<p>This is the default OS value.</p></td>
</tr>
<tr class="even">
<td><p>0</p></td>
<td><p>Clears the checkbox for <strong>Allow me to exchange Wi-Fi network access with my contacts</strong> during device OOBE.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-WiFiNetworkManager](microsoft-windows-wifinetworkmanager.md) | **DefaultAutoConnectSharedState**

## Valid Configuration Passes


offlineServicing

specialize

oobeSystem

## Applies To


Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-WiFiNetworkManager](microsoft-windows-wifinetworkmanager.md).

 

 






