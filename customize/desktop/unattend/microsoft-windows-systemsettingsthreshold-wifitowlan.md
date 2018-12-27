---
title: WiFiToWlan
description: WiFiToWlan
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 406f8115-d5f8-44d0-9af3-88768e5dfe21
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# WiFiToWlan


`WiFiToWlan` allows you to replace the "Wi-Fi" heading in the Networks list with "WLAN".

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Replaces the. &quot;Wi-Fi&quot; heading in the Networks list with &quot;WLAN&quot;.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>The &quot;Wi-Fi&quot; heading in the Networks list is unchanged. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-SystemSettingsThreshold](microsoft-windows-systemsettingsthreshold.md) | **WiFiToWlan**

## Applies To


For a full list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-SystemSettingsThreshold](microsoft-windows-systemsettingsthreshold.md).

## XML Example


The following XML output shows how to replace the "Wi-Fi" heading in the Networks list with "WLAN".

```
<WiFiToWlan>true</WiFiToWlan>
```

## Related topics


[Microsoft-Windows-SystemSettingsThreshold](microsoft-windows-systemsettingsthreshold.md)

 

 







