---
title: Xperf Actions
description: Xperf Actions
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 14ea91eb-eb7b-4dd7-a09d-da4743dc3805
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# Xperf Actions


Xperf actions are trace processing components that collate event information to produce text reports. Actions produce summarized reports that are specific to a set of events such as registry accesses, context switches, file accesses, or system configuration.

All actions are invoked using the following command-line pattern:

```
xperf -i input.etl -o output.txt -a <action_name> [action_parameters]
```

Where *input.etl* is the name of the trace file, *output.txt* is the name of the report file, and *&lt;action\_name&gt;* is the name of the action. The action name is always preceded by the `-a` command-line switch. The action name can be followed by one or more action-specific parameters.

## In This Section


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
<td><p>Shows boot and shut down statistics.</p></td>
</tr>
<tr class="even">
<td><p><a href="bootprefetch.md" data-raw-source="[bootprefetch](bootprefetch.md)">bootprefetch</a></p></td>
<td><p>Shows boot pre-fetching events.</p></td>
</tr>
<tr class="odd">
<td><p><a href="cpudisk.md" data-raw-source="[cpudisk](cpudisk.md)">cpudisk</a></p></td>
<td><p>Shows CPU/disk activity.</p></td>
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
<td><p>Shows a histogram of disk activity and idle times.</p></td>
</tr>
<tr class="odd">
<td><p><a href="dpcisr.md" data-raw-source="[dpcisr](dpcisr.md)">dpcisr</a></p></td>
<td><p>Shows deferred procedure call and interrupt service routine statistics.</p></td>
</tr>
<tr class="even">
<td><p><a href="drvdelay.md" data-raw-source="[drvdelay](drvdelay.md)">drvdelay</a></p></td>
<td><p>Shows driver delays.</p></td>
</tr>
<tr class="odd">
<td><p><a href="dumper.md" data-raw-source="[dumper](dumper.md)">dumper</a></p></td>
<td><p>Dumps events in text form.</p></td>
</tr>
<tr class="even">
<td><p><a href="filename-wpa.md" data-raw-source="[filename](filename-wpa.md)">filename</a></p></td>
<td><p>Shows file names.</p></td>
</tr>
<tr class="odd">
<td><p><a href="focuschange.md" data-raw-source="[focuschange](focuschange.md)">focuschange</a></p></td>
<td><p>Shows the Windows thread focus change events.</p></td>
</tr>
<tr class="even">
<td><p><a href="hardfault.md" data-raw-source="[hardfault](hardfault.md)">hardfault</a></p></td>
<td><p>Shows hard fault statistics by process and file.</p></td>
</tr>
<tr class="odd">
<td><p><a href="heap.md" data-raw-source="[heap](heap.md)">heap</a></p></td>
<td><p>Shows process heap information.</p></td>
</tr>
<tr class="even">
<td><p><a href="marks.md" data-raw-source="[marks](marks.md)">marks</a></p></td>
<td><p>Shows marks information.</p></td>
</tr>
<tr class="odd">
<td><p><a href="pagefault.md" data-raw-source="[pagefault](pagefault.md)">pagefault</a></p></td>
<td><p>Shows page fault information.</p></td>
</tr>
<tr class="even">
<td><p><a href="perfctrs.md" data-raw-source="[perfctrs](perfctrs.md)">perfctrs</a></p></td>
<td><p>Shows process performance counters.</p></td>
</tr>
<tr class="odd">
<td><p><a href="pnp.md" data-raw-source="[pnp](pnp.md)">pnp</a></p></td>
<td><p>Shows Plug and Play events.</p></td>
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
<td><p>Shows spinlock information.</p></td>
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
<td><p>Shows Winlogon events.</p></td>
</tr>
</tbody>
</table>

 

## Related topics


[Xperf Command-Line Reference](xperf-command-line-reference.md)

 

 







