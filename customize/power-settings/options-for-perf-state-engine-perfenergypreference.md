---
title: PerfEnergyPreference
description: PerfEnergyPreference specifies the value to program in the energy performance preference register on systems that implement version 2 of the CPPC interface.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 744AAF7E-E099-470C-85EC-3D901CA49407


ms.date: 10/05/2017
ms.topic: article


---

# PerfEnergyPreference


`PerfEnergyPreference` specifies the value to program in the energy performance preference register on systems that implement version 2 of the CPPC interface.

When set to 0, the energy performance preference register is programmed to 0 to favor performance. When set to 100, the energy performance preference register is set to 255 to favor energy savings. When set to an intermediate value, the energy performance preference register is programmed to the value: (setting \* 255) / 100.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `PerfEnergyPreference`

-   **PowerCfg:** `PERFEPP`

-   **Hidden setting:** Yes

## <span id="Values"></span><span id="values"></span><span id="VALUES"></span>Values


The value denotes percentage (%).

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Minimum value</p></td>
<td><p>0</p></td>
</tr>
<tr class="even">
<td><p>Maximum value</p></td>
<td><p>100</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


| Windows edition                                                        | x86-based devices | x64-based devices | ARM-based devices |
|------------------------------------------------------------------------|-------------------|-------------------|-------------------|
| Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) | x86               | amd64             | N/A               |
| Windows 10 Mobile                                                      | N/A               | N/A               | Supported         |
