---
title: Automatically wake for tasks
description: Specifies whether the system uses the system-wide wake-on-timer capability. The system can automatically use wake-on-timer on capable hardware to perform scheduled tasks. For example, the system might wake automatically to install updates.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 438B9775-99B4-40F7-B177-9B0FCC7E1CFE


ms.date: 10/05/2017
ms.topic: article


---

# Automatically wake for tasks


Specifies whether the system uses the system-wide wake-on-timer capability.

The system can automatically use wake-on-timer on capable hardware to perform scheduled tasks. For example, the system might wake automatically to install updates.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `AllowRtcWake `

-   **PowerCfg:** `RTCWAKE `

-   **GUID:** bd3b718a-0680-4d9d-8ab2-e1d2b4ac806d

-   **Hidden setting:** Yes

## <span id="Values"></span><span id="values"></span><span id="VALUES"></span>Values


<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Index</th>
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0</p></td>
<td><p>No</p></td>
<td><p>Wake on timer is disabled.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Yes</p></td>
<td><p>Wake on timer is enabled.</p></td>
</tr>
<tr class="odd">
<td><p>2</p></td>
<td><p>Important</p></td>
<td><p>Wake on internal system timers only.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


Available in Windows Vista and later versions of Windows.
