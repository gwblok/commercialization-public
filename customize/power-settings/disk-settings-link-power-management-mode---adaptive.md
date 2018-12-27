---
title: Link power management mode - adaptive
description: Specifies the period of AHCI link idle time before the link is put into a slumber state when Host-Initiated Power Management (HIPM) or Device-Initiated Power Management (DIPM) is enabled.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9FD82874-5D84-41D8-8B68-A73006A61323


ms.date: 10/05/2017
ms.topic: article


---

# <span id="p_customize_converged.disk_settings_link_power_management_mode_-_adaptive"></span>Link power management mode - adaptive


Specifies the period of AHCI link idle time before the link is put into a slumber state when Host-Initiated Power Management (HIPM) or Device-Initiated Power Management (DIPM) is enabled.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `N/A             `

-   **PowerCfg:** `N/A               `

-   **GUID:** dab60367-53fe-4fbc-825e-521d069d2456

-   **Hidden setting:** Yes

## <span id="Values"></span><span id="values"></span><span id="VALUES"></span>Values


The value denotes the number of milliseconds.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Minimum value</p></td>
<td><p>0 (Only use partial state)</p></td>
</tr>
<tr class="even">
<td><p>Maximum value</p></td>
<td><p>300,000 (5 minutes)</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


Available in Windows 7 and later versions of Windows.
