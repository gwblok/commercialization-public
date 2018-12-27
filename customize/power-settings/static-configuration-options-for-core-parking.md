---
title: Static configuration options for core parking
description: You can use the static configuration options documented in this section to tune the behavior of the core parking engine.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: E5A91698-3978-4BDB-8EB9-F8CA5382789D


ms.date: 10/05/2017
ms.topic: article


---

# Static configuration options for core parking


You can use the static configuration options documented in this section to tune the behavior of the core parking engine.

## <span id="in_this_section"></span>In this section


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Topic</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="options-for-core-parking-cpmincores.md" data-raw-source="[CPMinCores](options-for-core-parking-cpmincores.md)">CPMinCores</a></p></td>
<td><p><code>CPMinCores</code> specifies the minimum percentage of logical processors (in terms of all logical processors that are enabled on the system within each NUMA node) that can be placed in the un-parked state at any given time.</p></td>
</tr>
<tr class="even">
<td><p><a href="options-for-core-parking-cpmaxcores.md" data-raw-source="[CPMaxCores](options-for-core-parking-cpmaxcores.md)">CPMaxCores</a></p></td>
<td><p><code>CPMaxCores</code> specifies the maximum percentage of logical processors (in terms of logical processors within each NUMA node) that can be in the un-parked state at any given time.</p></td>
</tr>
<tr class="odd">
<td><p><a href="options-for-core-parking-cpincreasetime.md" data-raw-source="[CPIncreaseTime](options-for-core-parking-cpincreasetime.md)">CPIncreaseTime</a></p></td>
<td><p><code>CPIncreaseTime</code> specifies the minimum amount of time that must elapse before additional logical processors can be transitioned from the parked state to the unparked state. The time is specified in units of the number of processor performance time check intervals.</p></td>
</tr>
<tr class="even">
<td><p><a href="options-for-core-parking-cpdecreasetime.md" data-raw-source="[CPDecreaseTime](options-for-core-parking-cpdecreasetime.md)">CPDecreaseTime</a></p></td>
<td><p><code>CPDecreaseTime</code> specifies the minimum amount of time that must elapse before additional logical processors can be transitioned from the unparked state to the parked state. The time is specified in units of the number of processor performance time check intervals.</p></td>
</tr>
<tr class="odd">
<td><p><a href="options-for-core-parking-cpconcurrency.md" data-raw-source="[CPConcurrency](options-for-core-parking-cpconcurrency.md)">CPConcurrency</a></p></td>
<td><p><code>CPConcurrency</code> specifies the threshold for determining concurrency of the node.</p></td>
</tr>
<tr class="even">
<td><p><a href="options-for-core-parking-cpdistribution.md" data-raw-source="[CPDistribution](options-for-core-parking-cpdistribution.md)">CPDistribution</a></p></td>
<td><p><code>CPDistribution</code> specifies the utilization, in percentage, to use in the concurrency distribution to select the number of logical processors to distribute utility to.</p></td>
</tr>
<tr class="odd">
<td><p><a href="options-for-core-parking-cpheadroom.md" data-raw-source="[CPHeadroom](options-for-core-parking-cpheadroom.md)">CPHeadroom</a></p></td>
<td><p><code>CPHeadroom</code> specifies the value of utilization that would cause the core parking engine to unpark an additional logical processor if the least utilized processor out of the unparked set of processors had more utilization. This enables increases in concurrency to be detected.</p></td>
</tr>
<tr class="even">
<td><p><a href="options-for-core-parking-cplatencyhintunpark.md" data-raw-source="[CpLatencyHintUnpark](options-for-core-parking-cplatencyhintunpark.md)">CpLatencyHintUnpark</a></p></td>
<td><p><code>CPLatencyHintUnpark</code> specifies the minimum number of unparked cores when a system low latency hint is detected.</p></td>
</tr>
</tbody>
</table>
