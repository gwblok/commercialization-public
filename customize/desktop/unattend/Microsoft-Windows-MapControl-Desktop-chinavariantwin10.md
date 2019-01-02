---
title: ChinaVariantWin10
description: Use ChinaVariantWin10 to specify that the Windows device is intended to ship in China. When enabled, maps approved by the State Bureau of Surveying and Mapping in China are used, which are obtained from a server located in China.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: A15AA62C-9A5A-490E-A5CD-D0A435232664
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ChinaVariantWin10


Use `ChinaVariantWin10` to specify that the Windows device is intended to ship in China. When enabled, maps approved by the State Bureau of Surveying and Mapping in China are used, which are obtained from a server located in China.

This customization may result in different maps, servers, or other configuration changes on the device.

**Note**  If partners do not set the `ChinaVariantWin10` setting to 1, partners may not ship the device in China.

 

## Values


Set `ChinaVariantWin10` to one of the following values:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Maps approved by the State Bureau of Surveying and Mapping in China are used and the maps are obtained from a server located in China.</p></td>
</tr>
<tr class="even">
<td><p>0</p></td>
<td><p>Disables the feature.</p>
<p>This is the default OS value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-MapControl-Desktop](microsoft-windows-mapcontrol.md) | **ChinaVariantWin10**

## Applies to


For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-MapControl-Desktop](microsoft-windows-mapcontrol.md).

 

 






