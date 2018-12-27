---
title: HeteroDecreaseThreshold
description: HeteroDecreaseThreshold specifies a threshold to cross below, which is required to park the Nth efficiency class 1 core. There is a separate value for each core index. The threshold is relative to efficiency class 0 performance.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 438F7FD6-6795-45DD-988D-170E233F147D


ms.date: 10/05/2017
ms.topic: article


---

# HeteroDecreaseThreshold


`HeteroDecreaseThreshold` specifies a threshold to cross below, which is required to park the Nth efficiency class 1 core. There is a separate value for each core index. The threshold is relative to efficiency class 0 performance. The provisioning interface can specify up to 4 different thresholds. If the system has 5 or more class 1 cores, the 4th value is used for all remaining cores of the same class.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `HeteroDecreaseThreshold`

-   **PowerCfg:** `HETERODECREASETHRESHOLD`

-   **Hidden setting:** Yes

## <span id="Values"></span><span id="values"></span><span id="VALUES"></span>Values


`HeteroDecreaseThreshold` is a four-byte unsigned integer where each byte represents a threshold in percentage. The lowest byte is the first threshold. For example, to set four thresholds—A, B, C, and D—the value of the parameter will be A + B\*256 + C\*65536 + D\*16777216.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Minimum value</p></td>
<td><p>0 + 0<em>256 + 0</em>65536 + 0<em>16777216</p></td>
</tr>
<tr class="even">
<td><p>Maximum value</p></td>
<td><p>100 + 100</em>256 + 100<em>65536 + 100</em>16777216</p></td>
</tr>
</tbody>
</table>

 

## <span id="Applies_to"></span><span id="applies_to"></span><span id="APPLIES_TO"></span>Applies to


| Windows edition                                                        | x86-based devices | x64-based devices | ARM-based devices |
|------------------------------------------------------------------------|-------------------|-------------------|-------------------|
| Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) | x86               | amd64             | N/A               |
| Windows 10 Mobile                                                      | N/A               | N/A               | Supported         |
