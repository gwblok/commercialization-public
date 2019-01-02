---
title: Tools available
description: You can use tools that are available for Windows 8.1 Connected Standby to evaluate a Modern Standby system.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 012E92C9-4662-4A8A-855E-316C26B647C1

ms.date: 05/02/2017
ms.topic: article


---

# Tools available


You can use tools that are available for Windows 8.1 Connected Standby to evaluate a Modern Standby system. New flags are being added to help track whether a particular system that is returning data had the network stack up or not while in Standby mode. Some of the labels may be incorrect (for example, MS sessions identified as CS sessions). Please file bugs as issues are found.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Tool name</th>
<th>Description</th>
<th>Where available</th>
<th>When to use</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><code>Powercfg /sleepstudy</code></p></td>
<td><p>A powerful tool that can aid in your analysis of system behavior, and what components may be preventing a platform from reaching or maintaining the <a href="http://msdn.microsoft.com/library/windows/hardware/dn495346.aspx" data-raw-source="[lowest power states](http://msdn.microsoft.com/library/windows/hardware/dn495346.aspx)">lowest power states</a>.</p></td>
<td><p>Cmd tool available in Windows</p></td>
<td><p>To track system health and battery usage during Standby</p></td>
</tr>
<tr class="even">
<td><p><code>Powercfg /a</code></p></td>
<td><p>Reports the sleep states available on the computer. Reports reasons why sleep states are unavailable.</p></td>
<td><p>Cmd tool available in Windows</p></td>
<td><p>To verify the platform state enabled (CS vs. MS vs. S3)</p></td>
</tr>
<tr class="odd">
<td><p><a href="using-windows-performance-analyzer-to-analyze-modern-standby-issues.md" data-raw-source="[Windows Performance Analyzer](using-windows-performance-analyzer-to-analyze-modern-standby-issues.md)">Windows Performance Analyzer</a> (WPA)</p></td>
<td><p>WPA displays graphs and data tables of Event Tracing for Windows (ETW) events that are recorded by Windows Performance Recorder (WPR), Xperf, or an assessment that is run in the Assessment Platform. WPA can open any event trace log (ETL) file for analysis.</p></td>
<td><p>From Microsoft.com (available in ADK and SDK kits)</p></td>
<td><p>To analyze performance and DRIPS residency issues</p></td>
</tr>
<tr class="even">
<td><p>Connected Standby Assessment and Stress tests</p></td>
<td><p>These tests perform repeated transitions into and out of standby to ensure system health over time and prolonged usage.</p>
<p>The tests include:</p>
<ul>
<li><a href="https://msdn.microsoft.com/windows/hardware/commercialize/test/assessments/connected-standby-energy-efficiency" data-raw-source="[Connected Standby energy efficiency](https://msdn.microsoft.com/windows/hardware/commercialize/test/assessments/connected-standby-energy-efficiency)">Connected Standby energy efficiency</a></li>
<li><a href="https://msdn.microsoft.com/library/windows/hardware/dn949525" data-raw-source="[Connected Standby Duration Test](https://msdn.microsoft.com/library/windows/hardware/dn949525)">Connected Standby Duration Test</a></li>
<li><a href="https://msdn.microsoft.com/library/windows/hardware/dn940611" data-raw-source="[Connected Standby Exit Latency Stress](https://msdn.microsoft.com/library/windows/hardware/dn940611)">Connected Standby Exit Latency Stress</a></li>
<li><a href="https://msdn.microsoft.com/library/windows/hardware/dn940396" data-raw-source="[Connected Standby Hardware Security Test](https://msdn.microsoft.com/library/windows/hardware/dn940396)">Connected Standby Hardware Security Test</a></li>
<li><a href="https://msdn.microsoft.com/library/windows/hardware/dn942043" data-raw-source="[Connected Standby IO Stress](https://msdn.microsoft.com/library/windows/hardware/dn942043)">Connected Standby IO Stress</a></li>
<li><a href="https://msdn.microsoft.com/library/windows/hardware/dn924110" data-raw-source="[Connected Standby Stress with Driver Verifier&#39;s Concurrency Stress](https://msdn.microsoft.com/library/windows/hardware/dn924110)">Connected Standby Stress with Driver Verifier&#39;s Concurrency Stress</a></li>
</ul></td>
<td><p>HLK</p></td>
<td><p>To ensure reliable transitions into and out of standby</p></td>
</tr>
<tr class="odd">
<td><p>PowerShell</p></td>
<td><p>Can be used to query for storage reliability counters to inspect Load/Unload cycles.</p></td>
<td><p>Available in Windows</p></td>
<td><p>To ascertain the reliability impact a given Modern Standby usage pattern has on rotational reliability</p></td>
</tr>
</tbody>
</table>

 

Additional platform specific tools might be available from your silicon partner. Contact your silicon partner for additional details.

 

 






