---
title: DisplayNetworkSelection
description: DisplayNetworkSelection
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1c55dbf3-f812-4e0f-975e-787c4cf74be7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisplayNetworkSelection


`DisplayNetworkSelection` specifies whether to always show the Network Selection control in the **Mobile Broadband Properties** dialog. Normally, the Network Selection control is only shown when the computer is roaming.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Always show the Network Selection control in the <strong>Mobile Broadband Properties</strong> dialog.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Only show the Network Selection control in the <strong>Mobile Broadband Properties</strong> dialog when the computer is roaming. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-SystemSettingsThreshold](microsoft-windows-systemsettingsthreshold.md) | **DisplayNetworkSelection**

## Applies To


For a full list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-SystemSettingsThreshold](microsoft-windows-systemsettingsthreshold.md).

## XML Example


The following XML output shows how to always show the Network Selection control in the **Mobile Broadband Properties** dialog.

```
<DisplayNetworkSelection>true</DisplayNetworkSelection>
```

## Related topics


[Microsoft-Windows-SystemSettingsThreshold](microsoft-windows-systemsettingsthreshold.md)

 

 







