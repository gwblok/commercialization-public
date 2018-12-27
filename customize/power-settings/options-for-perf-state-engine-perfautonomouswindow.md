---
title: PerfAutonomousWindow
description: PerfAutonomousWindow specifies the value to program in the autonomous activity window register on systems that implement version 2 of the CPPC interface and have autonomous mode enabled.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: AB3DCB0C-0811-4AA8-9253-384EBFC9AFB1


ms.date: 10/05/2017
ms.topic: article


---

# PerfAutonomousWindow


`PerfAutonomousWindow` specifies the value to program in the autonomous activity window register on systems that implement version 2 of the CPPC interface and have autonomous mode enabled. Longer values indicate to the platform that it should be less sensitive to short duration spikes/dips in processor utilization.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `PerfAutonomousWindow`

-   **PowerCfg:** `PERFAUTONOMOUSWINDOW`

-   **Hidden setting:** Yes

## <span id="Values"></span><span id="values"></span><span id="VALUES"></span>Values


The value denotes microseconds.

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
<td><p>1,270,000,000</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


| Windows edition                                                        | x86-based devices | x64-based devices | ARM-based devices |
|------------------------------------------------------------------------|-------------------|-------------------|-------------------|
| Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) | x86               | amd64             | N/A               |
| Windows 10 Mobile                                                      | N/A               | N/A               | Supported         |
