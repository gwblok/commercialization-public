---
title: Keyword (in SystemProvider)
description: Keyword (in SystemProvider)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: afe8e6db-f5ad-4a94-9878-97840f91b8b2
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# Keyword (in SystemProvider)

Describes the kernel flags that can be enabled for the kernel-mode session.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[SystemProvider](systemprovider.md)\>
      * \<[Keywords (in SystemProvider)](keywords--in-systemprovider-.md)\>
        * \<**Keyword (in SystemProvider)**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[SystemCollectorId](systemcollectorid.md)\>
          * \<[SystemProviderId](systemproviderid.md)\>
            * \<[Keywords (in SystemProvider)](keywords--in-systemprovider-.md)\>
              * \<**Keyword (in SystemProvider)**\>
          * \<[SystemProvider](systemprovider.md)\>
            * \<[Keywords (in SystemProvider)](keywords--in-systemprovider-.md)\>
              * \<**Keyword (in SystemProvider)**\>


## Syntax

```
<Keyword Value = "AllFaults" | "CompactCSwitch" | "ContiguousMemorygeneration" | ... >
</Keyword>
```


## Attributes and Elements


### Attributes

| Attribute | Description                                                 | Data type                                    | Required | Default |
| :-------- | :---------------------------------------------------------- | :------------------------------------------- | :------- | :------ |
| **Value** | Describes the system Event Tracing for Windows (ETW) event. | See the Remarks section for possible values. | Yes      |         |


### Child Elements

None.


### Parent Elements

| Element                                                         | Description                                 |
| :-------------------------------------------------------------- | :------------------------------------------ |
| [Keywords (in SystemProvider)](keywords--in-systemprovider-.md) | Represents a collection of system keywords. |


## Remarks

The following table describes possible values for the **Value** attribute.

| Value                      | Description                                                                                                                                       |
| :------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------ |
| AllFaults                  | All faults are logged.                                                                                                                            |
| CompactCSwitch             | Used in connection with `CSwitch`, this reduces the information logged for each CSwitch, as well as uses differential compression and batching.   |
| ContiguousMemorygeneration | Contiguous memory generation is logged.                                                                                                           |
| CpuConfig                  | Changes in CPU configuration are logged.                                                                                                          |
| CSwitch                    | Context switch activity is logged.                                                                                                                |
| DiskIO                     | Disk I/O is logged.                                                                                                                               |
| DiskIOInitialization       | Disk I/O initialization is logged.                                                                                                                |
| DPC                        | Deferred procedure calls are logged.                                                                                                              |
| Drivers                    | Driver activity is logged.                                                                                                                        |
| FileIO                     | File I/O is logged.                                                                                                                               |
| FileIOInit                 | File I/O initialization is logged.                                                                                                                |
| Filename                   | The file name is logged.                                                                                                                          |
| FootPrint                  | Used to do memory analysis, this specifies to flush the working set on a special flush mark.                                                      |
| HardFaults                 | Hard faults are logged.                                                                                                                           |
| IdleStates                 | Idle states are logged.                                                                                                                           |
| Interrupt                  | Interrupts are logged.                                                                                                                            |
| KernelQueue                | Changes to the kernel queue are logged.                                                                                                           |
| Loader                     | Kernel and user mode load and unload events are logged.                                                                                           |
| Memory                     | Provides events about physical memory usage.                                                                                                      |
| MemoryInfo                 | Provides basic information about the memory manager, such as number of free, used, and standby pages, and so on.                                  |
| Pool                       | Changes to the memory pool are logged.                                                                                                            |
| Power                      | Power consumption is logged.                                                                                                                      |
| ProcessCounter             | Indicates that the profile has a process counter.                                                                                                 |
| ProcessThread              | Process and thread creation and deletion events are logged.                                                                                       |
| ReadyThread                | Ready thread events are logged.                                                                                                                   |
| Registry                   | Changes to the registry are logged.                                                                                                               |
| SampledProfile             | The profile is sampled.                                                                                                                           |
| SpinLock                   | Spinlock information is logged.                                                                                                                   |
| SplitIO                    | Provides events about split I/O requests. Single I/O requests can be split into multiple requests because of disk fragmentation or other reasons. |
| SystemCall                 | System calls are logged.                                                                                                                          |
| ThreadPriority             | Changes in thread priority are logged.                                                                                                            |
| Timer                      | Provides events about the system timer.                                                                                                           |
| VirtualAllocation          | Virtual memory allocation is logged.                                                                                                              |


## Related topics

[Elements](elements.md)

[CustomKeyword](customkeyword.md)

