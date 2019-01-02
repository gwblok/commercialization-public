---
title: WPR Command-Line Options
description: WPR Command-Line Options
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3c69c8df-6ce3-49a0-b17f-e2b60016b72a
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# WPR Command-Line Options

Windows Performance Recorder (WPR) offers a simple command line interface. The full complexity of WPR is embedded in the recording profiles.

## General options

WPR requires Windows 7 or later version operating system.

### Syntax

```
wpr FirstLevelOption [<arguments>] [Additional options [<arguments>]]
```

You can get additional help with:

```
wpr -help FirstLevelOption
```

The following FirstLevelOptions are available:


|          Option          |                                  Description                                   |
|--------------------------|--------------------------------------------------------------------------------|
|          -help           |                     Provide command line help information                      |
|        -profiles         |          Enumerates the profile names and descriptions from a profile          |
|       -purgecache        |                        Purges the dynamic symbols cache                        |
|          -start          |                          Starts one or more profiles.                          |
|         -marker          |                             Fires an event marker                              |
|       -markerflush       |               Fires an event marker and flushes the working set.               |
|         -status          |              Displays the status of an active recording (if any).              |
|     -profiledetails      |               Fires an event marker and flushes the working set.               |
|        -providers        |                 Displays detailed information about providers.                 |
|         -cancel          |                Cancels the recording initiated by WPR (if any).                |
|          -stop           |           Cancels and saves the recording initiated by WPR (if any).           |
|          -flush          |            Flushes the logging sessions initiated by WPR (if any).             |
|           -log           |            Configures the debug information saved to the event log.            |
| -disablepagingexecutive  |               Changes the **Disable Paging Executive** settings                |
|    -heaptracingconfig    |                   Changes a processes' heap tracing settings                   |
|     -snapshotconfig      |                     Change snapshot settings for a process                     |
|  -capturestateondemand   |   Captures the states of the configured providers in the current recording.    |
|       -pmcsources        |         Queries the list of hardware counters available on the system.         |
|       -setprofint        |                       Sets the sampled profile interval.                       |
|         -profint         |                     Queries the current profile interval.                      |
|      -resetprofint       |                 Restores the default profile interval values.                  |
|        -boottrace        |      Configures the registry entries for autologger/globallogger sessions      |
| -enableperiodicsnapshot  | Enables **Periodic Snapshot** for the specified interval and given process id. |
| -disableperiodicsnapshot |                 Disables **Periodic Snapshot** for all process                 |
|     -singlesnapshot      |             Gets an on-demand Snapshot for the specified process.              |

> [!NOTE]
> If you start WPR from the command line while another application is recording (such as Xperf or an application that uses NT Kernel Logger, such as logman or PerfTrace), WPR fails to start recording and returns the following error. In this case, you must cancel the other recording before you can start a new recording by using WPR:
>
> `The event collector was already running.`

## Profiles

The **Profiles** option lists the WPR profiles that the recording uses.

### Syntax

```
wpr -profiles [<path>]
```

The following table describes the available arguments that you can apply to this option. To see built-in profiles, omit the argument.

| Argument   | Description|
|:-----------|:-------------|
| *\<path\>* | Specifies the path and the name of the file that contains the profile definitions. For example: <br/><br/> `wpr -profiles “c:\Users\User1\Documents\WPR Files\Custom Profiles\CustomProfile1.wprp”` |

## Start

The **Start** option starts a recording by using one or more profiles.

### Syntax

```
wpr -start <profile> [-start <profilen>]... [-filemode] [-recordtempto <temp folder path>] [-onoffscenario <OnOff Transition Type>] [-onoffresultspath <path to which the trace files are saved>] [-onoffproblemdescription <description of the scenario>] [-numiterations <number of iterations for OnOff tracing>]
```

The following table describes the available switches that you can apply to this option.

| Switch| Description|
|:---------|:------------|
| *\<profile\>* \[**-start** *\<profilen\>*\]...| Specifies either a built-in profile or the path to a user-defined profile. You can specify up to 64 profiles on a single command line, with each profile specified as follows: <br/><br/>*\<profile\>* := \[*\<filename.wprp>*!\]*\<profile name\>*\[**.**{**light**\|**verbose**}\] <br/><br/> Each profile can define either light or verbose versions, or both versions. If neither option is specified, the verbose version is used unless the profile includes only a light version. |
| **-filemode**| Specifies that recording is done in file mode. (The default mode is memory.) By using this option, the data is recorded to an unbounded file, which can grow in size until it fills the disk.|
| **-recordtempto** *\<temp folder path\>*| Specifies the temporary folder path that the recording is saved to.|
| **-onoffscenario** *\<OnOff Transition Type\>*| Specifies one of the on/off transition types. These are: **Boot**, **FastStartup**, **Shutdown**, **RebootCycle**, **Standby**, or **Hibernate**.|
| **-onoffresultspath** *\<path to which the trace files are saved\>* | Specifies the path to which the trace files are saved.|
| **-onoffproblemdescription** *\<description of the scenario\>*      | Specifies the description of the scenario.|
| **-numiterations** *\<number of iterations for OnOff tracing\>*     | Sets the number of iterations for OnOff recording. By default, the settings from the built-in or custom profile file are used by default.|

## Stop

The **Stop** option stops the current recording and saves it to the file that is specified by the argument.

### Syntax

```
wpr -stop \<file\> \<problem description\>
```

The following table describes the available arguments that you can apply to this option.

| Argument| Description|
|:-----------|:------------|
| *\<file\>*| Specifies the event trace log (ETL) file to which WPR saves the recording. This argument is required.  |
| *\<problem description\>* | Specifies the problem description. Although this argument is optional, we recommended that you use it. |

## Cancel

The **Cancel** option cancels the current recording without saving the recorded data. If no instance is currently active, the **Cancel** option returns an error.

### Syntax

```
wpr -cancel
```

This option takes no arguments.

## Status

The **Status** option displays status information about the current WPR recording.

### Syntax

```
wpr -status [profiles] [collectors [details]]
```

If no recording is currently active, a message displays that WPR is not recording. If a recording is currently active and no arguments are used, the following status information displays:

```
WPR recording is in progress...

Time since start        : 00:04:27

Dropped event           : 0

Logging mode            : Memory
```

If you supply arguments together with the **–status** option, the information listed above displays together with data that is specific to that option. The following table describes the available arguments that you can apply to this option.

<table>
<thead valign="bottom">
<tr class="header">
<th>Argument</th>
<th>Description and Example Output</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><em>profiles</em></td>
<td>This argument lists each profile that is being used in the current WPR recording.
<p><strong>Example:</strong></p>
<pre class="syntax" space="preserve">Recording system activity using the following set of profiles:

Profile                 : CPU.Verbose.Memory</pre></td>
</tr>
<tr class="even">
<td><em>collectors</em></td>
<td>Lists collector information. If buffers have been lost, those buffers are listed.
<p><strong>Example:</strong></p>
<pre class="syntax" space="preserve">Actively recording collectors:

Collector Name          : NT Kernel Logger
Buffer Size (KB)        : 1024
Events Lost             : 0
System Keywords
        CSwitch
        ProcessThread
        SampledProfile
System Stacks
        CSwitch
        SampledProfile

Collector Name          : WPR_initiated_WPR Event Collector
Buffer Size (KB)        : 1024
Events Lost             : 0
Providers
        Microsoft-Windows-Shell-Core: 0x1000000000000: 0x04
        Microsoft-Windows-Win32k: 0x1000000402000: 0xff : Stack
CaptureState Providers on Save
        Microsoft-Windows-Win32k: 0x80000: 0xff</pre></td>
</tr>
<tr class="odd">
<td><em>details</em></td>
<td>Lists additional information about each collector.</td>
</tr>
</tbody>
</table>

## Profiledetails

The **Profiledetails** option displays detailed information about a profile or set of profiles. To specify multiple profiles, use the following syntax where *\<profilen\>* refers to the name of each profile.

### Syntax

```
wpr -profiledetails <profile1>+<profile2>+...+<profilen> [-filemode] -onoffscenario <OnOff Transition Type>
```

The following table describes the available switches that you can apply to this option.

| Switch| Description|
|:-----------|:---------|
| **-filemode**| Specifies that recording was done in file mode. (The default mode is memory.)                                                                     |
| **-onoffscenario** *\<OnOff Transition Type\>* | Specifies one of the on/off transition types. These are: **Boot**, **FastStartup**, **Shutdown**, **RebootCycle**, **Standby**, or **Hibernate**. |

## Providers

The **Providers** option displays detailed information about providers. Providers refer to the Event Tracing for Windows (ETW) components that expose events to Windows Performance Recorder (WPR). To display information about providers, use the following syntax, where **-providers** refers to all installed/known and registered providers.

### Syntax

```
wpr -providers
```

This option takes no arguments.

## Boottrace

The **Boottrace** option configures the registry entries for autologger/globallogger sessions for the given profile.

### Syntax

```
wpr -boottrace {-addboot [<filename.wprp>!]<profile> [-addboot <profile> ...] [-filemode] [-recordtempto <temp folder path>] | -stopboot <recording filename> <Problem description> | -cancelboot}
```

The following table describes the available keywords that you can apply to this option.

<table width="80%">
<thead>
<tr >
<th>Keyword</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td width="30%"><b>-addboot</b></td>
<td>Sets the autologger registry entries for the given profile.  The <code>wpr -addboot</code> command takes the same options as the <code>wpr -start</code> command. Note that this options does not immediately start the trace. After reboot, the autologger will be started by the operating system.</td>
</tr>
<tr>
<td><b>-stopboot</b></td>
<td>Removes the autologger configured by <strong>addboot</strong>, stops the boot recording and merges all the recording into the given file. Note that this option saves the trace only if the autologger session is running (i.e. after reboot). Otherwise, this option will remove only the autologger configuration.</td>
</tr>
<tr>
<td><b>-cancelboot</b></td>
<td>Removes the autologger configured by <strong>addboot</strong> and cancels the boot recording initiated by WPR.</td>
</tr>
</tbody>
</table>

## CaptureStateOnDemand

The **CaptureStateOnDemand** option captures states for the configured providers in the current recording. The event provider should be configured for **capturestateondemand** within the profile file while the session is running.

### Syntax

```
wpr-capturestateondemand
```

Below is an example of **EventProvider**:

```
<EventProvider Id="EventProvider_Microsoft-Windows-Win32k" Name="Microsoft-Windows-Win32k" NonPagedMemory="true" CaptureStateOnly="true">
      <CaptureStateOnDemand Timeout="5">
         <Keyword Value="0x0"/>
      </CaptureStateOnDemand>
    </EventProvider>
```

## Marker

The **Marker** option fires an event marker with the given text in the current system logging session.

### Syntax

```
wpr -marker <text>
```

## MarkerFlush

The **MarkerFlush** option fires an event marker with the given text and flushes the working set.

### Syntax

```
wpr -markerflush <text>
```

## Flush

The **Flush** option flushes logging sessions to files initiated through WPR.

### Syntax

```
wpr -flush
```

This option takes no arguments.

## HeapTracingConfig

The **HeapTracingConfig** option enables or disables heap tracing for a specific process or store application.

### Syntax

```
wpr -HeapTracingConfig <process name> [<package full name> <package relative app ID>] [{enable|disable}]
```

> [!NOTE]
> * If the {**enable**|**disable**} parameter is omitted, the current heap tracing configuration for the process or app will be displayed. For example: `wpr -HeapTracingConfig Heaptest.exe enable`
> * This command doesn’t immediately start the trace, and should be executed before taking the heap trace. See [Recording for Heap Analysis](https://docs.microsoft.com/windows-hardware/test/wpt/recording-for-heap-analysis) for more details.
> * Always disable **HeapTracingConfig** for the process after tracing is done since it can impact the performance of the process.

## Disablepagingexecutive

The **Disablepagingexecutive** option specifies whether drivers and kernel-mode system code can be paged to disk. Setting this option to **on** prevents paging.
This option sets the value of [DisablePagingExecutive](https://technet.microsoft.com/en-us/library/cc959492.aspx) in the registry.

### Syntax

```
wpr -disablepagingexecutive {on | off}
```

> [!NOTE]
> To correctly capture event stacks on 64-bit systems that are running Windows 7, **disablepagingexecutive** should be set to **On**, and the system must be rebooted before you start performance recording. For 32-bit systems that are running Windows 7 and for all systems that are running Windows 8 or higher, you can operate performance recording without setting **disablepagingexecutive** to **On**.

## Log

The **Log** option appends and configures debug logging to the event log.

### Syntax

```
wpr -log {enabled | disabled | remove}
```

The following table describes the available keywords that you can apply to this option.

| Keyword      | Description|
|:-------------|:--------------|
| **enabled**  | Enables debug logging to the event log|
| **disabled** | Disables debug logging to the event log|
| **remove**   | Uninstalls the WPR debug logging provider manifest from the system|

## Purgecache

The **Purgecache** option purges the managed symbols cache.

### Syntax

```
wpr -purgecache
```

This option takes no arguments.

## Help

Use this option to display on-line help in the Command Prompt window.

### Syntax

```
wpr -help [{boottrace | cancel | capturestateondemand | disablepagingexecutive | disableperiodicsnapshot | flush | heaptracingconfig | snapshotconfig | log | marker | markerflush | pmcsources | profiledetails | profiles | providers | purgecache | start | status | stop}]
```

The following table describes the available keywords that you can apply to this option.

|Keyword|Description|
|:----------|:----|
|**No keyword**|Displays a list of options and short descriptions. To get further help for specific options, use a keyword. For example: `wpr -help start`. |
|**cancel**|Describes the **–cancel** command-line argument. For more information, see [Cancel](#cancel).|
|**disablepagingexecutive**|Describes the *–disablepagingexecutive** command-line argument. For more information, see [Disablepagingexecutive](#disablepagingexec).|
|**log**| Describes **-log** command-line arguments. For more information, see [Log](#log).|
| **profiledetails**| Describes the **–profiledetails** command-line argument. For more information, see [Profiledetails](#prodet).|
| **profiles**| Describes **-profiles** command-line arguments. For more information, see [Profiles](#profiles).|
| **providers**| Describes the **-providers** command-line argument. For more information, see [Providers](#providers).|
| **purgecache**| Describes the **–purgecache** command-line argument. For more information, see [Purgecache](#purge).|
| **start**| Presents descriptions of **-start** command-line arguments. For more information, see [Start](#start).|
| **status**| Presents descriptions of **-status** command-line arguments. For more information, see [Status](#status).|
| **stop**| Describes **-stop** command-line arguments. For more information, see [Stop](#stop).|

## SnapshotConfig

The **SnapshotConfig** option enables or disables the ability to capture one-time or periodic snapshots of *\<snapshot option>*\ for a specific process or processes. Currently you can take take snapshots of the heap.

### Syntax

```
wpr -SnapshotConfig <snapshot option> {-name <process name> | -pid <pid 1> [pid 2] ...} [{enable|disable}]
```

If the `{enable|disable}` parameter is omitted, the current snapshot configuration for the process will be displayed (i.e. only the **-name** option).

This example uses the **snapshotconfig** command with image names:

```
wpr -snapshotconfig heap -name Win32Project1.exe           //query snapshot config
wpr -snapshotconfig heap -name Win32Project1.exe enable    //enable snapshot config
wpr -snapshotconfig heap -name Win32Project1.exe disable   //disable snapshot config
```

This example uses the **snapshotconfig** command with a PID:

```
wpr -snapshotconfig heap -pid 8048 enable                //enable snapshot config
```

> [!NOTE]
> If the process and OS architecture does not match match (for example, a win32 app on a 64bit Operating system), use the image name option.

The following table describes the available switches that you can apply to this option.

| Switch | Description |
| -- | -- |
| *\<snapshot option\>* | Specifies one of the snapshot option types. Currently only the Heap is available. |
| **-name** | Specifies the name of process. This switch cannot be used with **-Pid** switch. If this switch is used to enable the snapshot, the config will apply to all new instances of the specified process name. Please be sure to disable it when the testing has finished.  |
| **-pid** | Specifies the process id. This switch cannot be used with -name switch. If this switch is used to enable the snapshot, the configuration will be applied immediately and for the lifetime of the process. |

## SingleSnapshot

The **SingleSnapshot** option triggers an on-demand snapshot of *\<snapshot option\>* for specified process ID.

### Syntax

```
wpr -SnapshotConfig <snapshot option> <pid 1> [pid 2] ... [up to pid 8]
```

> [!NOTE]
> The snapshot feature needs to be enabled for the process id (or name) before calling **SingleSnapshot**.
>
>For example: `wpr -singlesnapshot heap <pid for foo.exe>`
>
>Please refer to [SnapshotConfig](#snapshotconfig) command for more information.

The following table describes the available switches that you can apply to this option.

| Switch | Description |
| --- | --- |
| *\<snapshot option\>* | Specifies one of the snapshot option type. |
| \<pid\> | Specifies the process id. |

## EnablePeriodicSnapshot

The **EnablePeriodicSnapshot** option triggers periodic snapshots at specified intervals and given process IDs

### Syntax

```
wpr -enableperiodicsnapshot <snapshot option> <interval (in seconds)> <pid 1> [pid 2] ... [up to pid 8]
```

> [!NOTE]
> The snapshot feature needs to be enabled for the process id (or name) before calling **SingleSnapshot**.
>
>For example: `wpr -enableperiodicsnapshot heap 60 <pid for foo.exe>`
>
>Please refer to SnapshotConfig command for more information.

The following table describes the available switches that you can apply to this option.

| Switch | Description |
| --- | --- |
| *\<snapshot option\>* | Specifies one of the snapshot option type. |
| \<interval\> | Specifies the interval in seconds. Note that the minimum valid interval is 5. |
| \<pid\> | Specifies the process id. |

## DisablePeriodicSnapshot

The **DisablePeriodicSnapshot** option disables periodic snapshots for all processes specified by the **enableperiodicsnapshot** option.

### Syntax

```
wpr -disableperiodicsnapshot <snapshot option>
```

### Example

```
wpr -disableperiodicsnapshot heap
```

The following table describes the available switches that you can apply to this option.

|Switch | Description |
| -- | -- |
| \<snapshot option\> | Specifies one of the snapshot option types. |
|

## PMCSources

The **PMCSources** option queries the list of hardware counters on the system and their default sampling rates.

### Syntax

```
wpr -pmcsources
```

> [!NOTE]
> Performance Monitor Unit events are used to measure CPU performance and understand workloads CPU characterization. Only a subset of PMU events in ARM/intel reference documents are implemented in Windows HAL. The example output of this option on Intel CPU device is below:

```
C:\Program Files (x86)\Windows Kits\10\Windows Performance Toolkit>wpr -pmcsources
Id  Name                        Interval  Min      Max
--------------------------------------------------------------
  0 Timer                          10000  1221    1000000
  2 TotalIssues                   698400  4096 2147483647
  6 BranchInstructions             65536  4096 2147483647
 10 CacheMisses                    65536  4096 2147483647
 11 BranchMispredictions           65536  4096 2147483647
 19 TotalCycles                    65536  4096 2147483647
 25 UnhaltedCoreCycles             65536  4096 2147483647
 26 InstructionRetired             65536  4096 2147483647
 27 UnhaltedReferenceCycles        65536  4096 2147483647
 28 LLCReference                   65536  4096 2147483647
 29 LLCMisses                      65536  4096 2147483647
 30 BranchInstructionRetired       65536  4096 2147483647
 31 BranchMispredictsRetired       65536  4096 2147483647
 32 LbrInserts                     65536  4096 2147483647
```

## ProfInt

The **ProfInt** option queries the “profiling” interval.

### Syntax

```
wpr -profint
```

### Example

```
C:\Program Files (x86)\Windows Kits\10\Windows Performance Toolkit>wpr -profint
Current Profile Interval = 10000 [1.0000ms]
```

## SetProfInt

The **SetProfInt** option sets the sampled profile interval in 100 ns units.

### Syntax

```
wpr -setprofint <n> [1221...10000000\]
```

### Example

```
C:\Program Files (x86)\Windows Kits\10\Windows Performance Toolkit>wpr -setprofint 100000
New Profile Interval = 100000 [10.0000ms]
```

## ResetProfInt

The **ResetProfInt** option resets the profile interval to the default value.

### Syntax

```
wpr -resetprofint \[Profile Source Name\]
```

Note that if *[Profile Source Name]* is not provided, all profile sources will be reset to the default value.

## Instancename

The **Instancename** option specifies a name to uniquely identify the tracing instance.

This option can be applied to any commands that manipulate the logging session and assigns a user supplied logging session name. WPR sets the default session name if this option is omitted.

### Syntax

```
wpr –{option <arguments>} -instancename <text>
```

> [!NOTE]
> **-instancename** must be the last parameter. If the logging sessions were started with this option, all the subsequent commands should use the same instancename option. For example:

```
C:\wpt>wpr -start cpu -instancename CpuSession
C:\wpt>wpr -status
WPR recording is in progress...
...
Time since start        : 00:00:05
Dropped event           : 0
Logging mode            : Memory
C:\wpt>wpr -stop cpu.etl  -> omitting instancename option would not find CpuSession
        There are no trace profiles running.
        Error code: 0xc5583000
C:\wpt>wpr -stop cpu.etl -instancename CpuSession  -> trace will be saved
```

## Remarks

Each time that WPR saves a trace that was captured when managed applications were running on the system, WPR saves managed symbols next to the trace file. This feature enables performance analysis of managed applications.

Generating managed symbols is a resource- and time-consuming operation. WPR automatically creates a managed symbol cache to expedite the generation of managed symbols. When WPR needs managed symbols, it first checks this cache and uses any available and appropriate symbols instead of regenerating them.

The default managed symbol cache location is C:\\ProgramData\\WindowsPerformanceRecorder\\NGenPdbs\_Cache.

## Related topics

[WPR Reference](wpr-reference.md)
