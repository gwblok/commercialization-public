---
title: Static configuration options for heterogeneous power scheduling
description: You can use the static configuration options documented in this section to tune the core parking engine on heterogeneous systems.Note  These settings are only valid for class 1 cores and replace CP\_CONCURRENCY, PARK\_DISTRIBUTION\_THRESHOLD and CP\_HEADROOM.  .
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2CE6A0EA-C069-4162-B087-C39264FBD8BF


ms.date: 10/05/2017
ms.topic: article


---

# Static configuration options for heterogeneous power scheduling


You can use the static configuration options documented in this section to tune the core parking engine on heterogeneous systems.

**Note**  These settings are only valid for class 1 cores and replace CP\_CONCURRENCY, PARK\_DISTRIBUTION\_THRESHOLD and CP\_HEADROOM.

 

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
<td><p><a href="configuration-for-hetero-power-scheduling-heteroincreasethreshold.md" data-raw-source="[HeteroIncreaseThreshold](configuration-for-hetero-power-scheduling-heteroincreasethreshold.md)">HeteroIncreaseThreshold</a></p></td>
<td><p><code>HeteroIncreaseThreshold</code> specifies the threshold value to cross above, which is required to unpark the Nth efficiency class 1 core. There is a separate value for each core index. The threshold is relative to efficiency class 0 performance.</p></td>
</tr>
<tr class="even">
<td><p><a href="configuration-for-hetero-power-scheduling-heterodecreasethreshold.md" data-raw-source="[HeteroDecreaseThreshold](configuration-for-hetero-power-scheduling-heterodecreasethreshold.md)">HeteroDecreaseThreshold</a></p></td>
<td><p><code>HeteroDecreaseThreshold</code> specifies a threshold to cross below, which is required to park the Nth efficiency class 1 core. There is a separate value for each core index. The threshold is relative to efficiency class 0 performance.</p></td>
</tr>
<tr class="odd">
<td><p><a href="configuration-for-hetero-power-scheduling-heteroincreasetime.md" data-raw-source="[HeteroIncreaseTime](configuration-for-hetero-power-scheduling-heteroincreasetime.md)">HeteroIncreaseTime</a></p></td>
<td><p><code>HeteroIncreaseTime</code> specifies the minimum amount of time that must elapse before additional efficiency class 1 logical processors can be transitioned form the parked state to the unparked state. The time is specified in processor performance time check intervals.</p></td>
</tr>
<tr class="even">
<td><p><a href="configuration-for-hetero-power-scheduling-heterodecreasetime.md" data-raw-source="[HeteroDecreaseTime](configuration-for-hetero-power-scheduling-heterodecreasetime.md)">HeteroDecreaseTime</a></p></td>
<td><p><code>HeteroDecreaseTime</code> specifies the minimum amount of time that must elapse before additional efficiency class 1 logical processors can be transitioned from the unparked state to the parked state. The time is specified in performance time check intervals.</p></td>
</tr>
<tr class="odd">
<td><p><a href="configuration-for-hetero-power-scheduling-heteroclass1initialperf.md" data-raw-source="[HeteroClass1InitialPerf](configuration-for-hetero-power-scheduling-heteroclass1initialperf.md)">HeteroClass1InitialPerf</a></p></td>
<td><p><code>HeteroClass1InitialPerf</code> specifies the initial performance percentage of the efficiency class 1 core when this core is unparked.</p></td>
</tr>
<tr class="even">
<td><p><a href="configuration-for-hetero-power-scheduling-heteroclass0floorperf.md" data-raw-source="[HeteroClass0FloorPerf](configuration-for-hetero-power-scheduling-heteroclass0floorperf.md)">HeteroClass0FloorPerf</a></p></td>
<td><p><code>HeteroClass0FloorPerf</code> specifies the performance level floor, in percentage, to use for efficiency class 0 processors if there is at least one unparked efficiency class 1 processor.</p></td>
</tr>
</tbody>
</table>
