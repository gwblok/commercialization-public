---
title: Sleep unattended idle timeout
description: Specifies the duration of inactivity before the system automatically enters sleep after waking from sleep in an unattended state.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4B2FE163-497B-42A2-A43D-5284CB9FF5EB


ms.date: 10/05/2017
ms.topic: article


---

# Sleep unattended idle timeout


Specifies the duration of inactivity before the system automatically enters sleep after waking from sleep in an unattended state.

For example, if the system wakes from sleep because of a timed event or a wake on LAN (WoL) event, the sleep unattended idle timeout value will be used instead of the [sleep idle timeout](sleep-settings-sleep-idle-timeout.md) value.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `UnattendTimeout     `

-   **PowerCfg:** `UnattendTimeout       `

-   **GUID:** 7bc4a2f9-d8fc-4469-b07b-33eb785aaca0

-   **Hidden setting:** Yes

## <span id="Values"></span><span id="values"></span><span id="VALUES"></span>Values


The value denotes the number of seconds.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Minimum value</p></td>
<td><p>0 (Never idle to sleep)</p></td>
</tr>
<tr class="even">
<td><p>Maximum value</p></td>
<td><p>Maximum integer</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


Available in Windows Vista with Service Pack 1 (SP1), Windows Server 2008 R2, and later versions of Windows.
