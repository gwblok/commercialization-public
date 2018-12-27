---
title: PerfLatencyHint
description: PerfLatencyHint specifies the processor performance in response to latency sensitivity hints.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2EFD8F13-E9F7-4E16-A6B1-4F625FE162C7


ms.date: 10/05/2017
ms.topic: article


---

# PerfLatencyHint


`PerfLatencyHint` specifies the processor performance in response to latency sensitivity hints. Such hints are generated when an event preceding an expected latency-sensitive operation is detected. Examples include mouse button up events (for all mouse buttons), touch gesture start and gesture stop (finger down and finger up), and keyboard enter key down.

When set to 0, the processor performance engine does not take latency sensitivity hints to account when selecting a performance state. Otherwise, the performance is raised system-wide to the specified performance level.

## <span id="Aliases_and_setting_visibility"></span><span id="aliases_and_setting_visibility"></span><span id="ALIASES_AND_SETTING_VISIBILITY"></span>Aliases and setting visibility


-   **Windows Provisioning:** `PerfLatencyHint`, `PerfLatencyHint1`

-   **PowerCfg:** `LATENCYHINTPERF`, `LATENCYHINTPERF1`

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
