---
title: processing
description: processing
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: effacd2f-9804-434e-bbd9-128cddd7f940
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# processing


Displays trace post-processing options.

```
xperf -i <trace file>… [-o output] [-symbols …] [-target {human|machine}] [-a action …[-a action …] …]
```

## Parameters


<a href="" id="-itrace-file"></a>**-i***trace file*  
The trace file to be processed.

<a href="" id="-ooutput-file"></a>**-o***output file*  
The name of the output file. If not given, **stdout** is used.

<a href="" id="-symbols-options-"></a>**-symbols**<em>\[options\]</em>  
Enable and configure symbol decoding support. For more information see [symbols](symbols.md).

<a href="" id="-target-human-machine-"></a>**-target**<em>{human|machine}</em>  
Select the target audience of the output. The default value is "human".

<a href="" id="-quiet"></a>**-quiet**  
Do not print progress information.

<a href="" id="-tle"></a>**-tle**  
Process the trace even in the presence of lost events. The acronym *TLE* stands for *tolerate lost events*.

<a href="" id="-tti"></a>**-tti**  
Process the trace even in the presence of time inversions. The acronym *TTI* stands for *tolerate time inversions*.

<a href="" id="-aaction----"></a>**-a***action ...*  
The actions to take. The default action is to dump the event in text form.

## Remarks


The following table describes available actions.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Action</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="boot.md" data-raw-source="[boot](boot.md)">boot</a></p></td>
<td><p>Shows boot and shutdown statistics.</p></td>
</tr>
<tr class="even">
<td><p><a href="bootprefetch.md" data-raw-source="[bootprefetch](bootprefetch.md)">bootprefetch</a></p></td>
<td><p>Shows boot-time prefetching information.</p></td>
</tr>
<tr class="odd">
<td><p><a href="cpudisk.md" data-raw-source="[cpudisk](cpudisk.md)">cpudisk</a></p></td>
<td><p>Shows CPU/disk activity report.</p></td>
</tr>
<tr class="even">
<td><p><a href="cswitch.md" data-raw-source="[cswitch](cswitch.md)">cswitch</a></p></td>
<td><p>Shows context switch data.</p></td>
</tr>
<tr class="odd">
<td><p><a href="diskio.md" data-raw-source="[diskio](diskio.md)">diskio</a></p></td>
<td><p>Shows disk I/O statistics.</p></td>
</tr>
<tr class="even">
<td><p><a href="diskidlehistogram.md" data-raw-source="[diskidlehistogram](diskidlehistogram.md)">diskidlehistogram</a></p></td>
<td><p>Shows all disk activity and idle times in histogram format.</p></td>
</tr>
<tr class="odd">
<td><p><a href="dpcisr.md" data-raw-source="[dpcisr](dpcisr.md)">dpcisr</a></p></td>
<td><p>Show DPC/ISR statistics.</p></td>
</tr>
<tr class="even">
<td><p><a href="drvdelay.md" data-raw-source="[drvdelay](drvdelay.md)">drvdelay</a></p></td>
<td><p>Shows driver delays.</p></td>
</tr>
<tr class="odd">
<td><p><a href="dumper.md" data-raw-source="[dumper](dumper.md)">dumper</a></p></td>
<td><p>Dumps events in the trace in text form.</p></td>
</tr>
<tr class="even">
<td><p><a href="filename-wpa.md" data-raw-source="[filename](filename-wpa.md)">filename</a></p></td>
<td><p>Show file names in the trace.</p></td>
</tr>
<tr class="odd">
<td><p><a href="focuschange.md" data-raw-source="[focuschange](focuschange.md)">focuschange</a></p></td>
<td><p>Shows the Windows thread focus change events in the trace.</p></td>
</tr>
<tr class="even">
<td><p><a href="hardfault.md" data-raw-source="[hardfault](hardfault.md)">hardfault</a></p></td>
<td><p>Shows hard fault statistics by process and file.</p></td>
</tr>
<tr class="odd">
<td><p><a href="heap.md" data-raw-source="[heap](heap.md)">heap</a></p></td>
<td><p>Shows heap information.</p></td>
</tr>
<tr class="even">
<td><p><a href="marks.md" data-raw-source="[marks](marks.md)">marks</a></p></td>
<td><p>Shows marks information.</p></td>
</tr>
<tr class="odd">
<td><p><a href="pagefault.md" data-raw-source="[pagefault](pagefault.md)">pagefault</a></p></td>
<td><p>Shows page fault information in the trace.</p></td>
</tr>
<tr class="even">
<td><p><a href="perfctrs.md" data-raw-source="[perfctrs](perfctrs.md)">perfctrs</a></p></td>
<td><p>Shows process performance counters.</p></td>
</tr>
<tr class="odd">
<td><p><a href="pnp.md" data-raw-source="[pnp](pnp.md)">pnp</a></p></td>
<td><p>Shows Plug and Play events in the trace.</p></td>
</tr>
<tr class="even">
<td><p><a href="prefetch.md" data-raw-source="[prefetch](prefetch.md)">prefetch</a></p></td>
<td><p>Shows prefetch information.</p></td>
</tr>
<tr class="odd">
<td><p><a href="process.md" data-raw-source="[process](process.md)">process</a></p></td>
<td><p>Shows process, thread, and image information.</p></td>
</tr>
<tr class="even">
<td><p><a href="profile-wta.md" data-raw-source="[profile](profile-wta.md)">profile</a></p></td>
<td><p>Shows sampled profiler data.</p></td>
</tr>
<tr class="odd">
<td><p><a href="registry.md" data-raw-source="[registry](registry.md)">registry</a></p></td>
<td><p>Shows registry access statistics.</p></td>
</tr>
<tr class="even">
<td><p><a href="services.md" data-raw-source="[services](services.md)">services</a></p></td>
<td><p>Shows service status information.</p></td>
</tr>
<tr class="odd">
<td><p><a href="shutdown.md" data-raw-source="[shutdown](shutdown.md)">shutdown</a></p></td>
<td><p>Shows shutdown statistics.</p></td>
</tr>
<tr class="even">
<td><p><a href="spinlock.md" data-raw-source="[spinlock](spinlock.md)">spinlock</a></p></td>
<td><p>Shows information relevant to spinlock activity.</p></td>
</tr>
<tr class="odd">
<td><p><a href="stack.md" data-raw-source="[stack](stack.md)">stack</a></p></td>
<td><p>Shows stack information.</p></td>
</tr>
<tr class="even">
<td><p><a href="suspend.md" data-raw-source="[suspend](suspend.md)">suspend</a></p></td>
<td><p>Shows suspend transition information.</p></td>
</tr>
<tr class="odd">
<td><p><a href="sysconfig.md" data-raw-source="[sysconfig](sysconfig.md)">sysconfig</a></p></td>
<td><p>Shows system configuration information.</p></td>
</tr>
<tr class="even">
<td><p><a href="tracestats.md" data-raw-source="[tracestats](tracestats.md)">tracestats</a></p></td>
<td><p>Shows trace statistics.</p></td>
</tr>
<tr class="odd">
<td><p><a href="winlogon.md" data-raw-source="[winlogon](winlogon.md)">winlogon</a></p></td>
<td><p>Shows Windows logon events in the trace.</p></td>
</tr>
</tbody>
</table>

 

If no action is present, **dumper** is invoked.

## Example


The following table shows examples of **processing**.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>xperf -i trace.etl -o out.csv</code></p></td>
<td><p>Dumps the events in trace.etl to the Out.csv file.</p></td>
</tr>
<tr class="even">
<td><p><code>xperf -help registry</code></p></td>
<td><p>Prints Help for the <strong>registry</strong> action.</p></td>
</tr>
<tr class="odd">
<td><p><code>xperf -i trace.etl -a registry</code></p></td>
<td><p>Prints registry access statistics to <strong>stdout</strong>.</p></td>
</tr>
<tr class="even">
<td><p><code>xperf -i trace32.etl trace64.etl -o out.csv</code></p></td>
<td><p>Dumps the events in Trace32.etl and Trace64.etl to the Out.csv file.</p></td>
</tr>
</tbody>
</table>

 

## Related topics


[Xperf Options](xperf-options.md)

 

 







