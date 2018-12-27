---
title: Evaluating spinlock data
description: Evaluating spinlock data
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9e5e4ffa-5fb7-401e-bfc3-760cbb7955d9
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# Evaluating spinlock data


The spinlock report presents the following information about spinlocks:

-   Acquire sample rate
-   Contention sample rate
-   Spin threshold
-   Number of CPUs
-   CPU speed, in megahertz
-   Trace length, in nanoseconds
-   Trace length, in cycles


## Spinlock report sections

The next sections of the report show the spinlock usage during the profile time period.


### Individual spinlocks

Each spinlock is shown separately. Spinlocks are sorted with the "hottest" spinlocks shown first. Often it is possible to identify the spinlock bottleneck by looking at the top few spinlocks.

The following information is presented for each spinlock:

-   Type of lock
-   Kernel address of lock
-   Symbol of the lock (note that spinlocks created dynamically do not have symbols)


### Summary report section

A summary report follows with the following information:

-   Percentage of CPU time spent on lock acquisition
-   Percentage of CPU time spent on lock contention
-   Lock acquisition rate
-   Collision rate
-   Spin rate
-   Contention rate, both sampled and normalized

The final two sections of the report are the events skipped due to interrupts and the release function.


### Events skipped due to interrupts

Interrupts can occur while spinlocks are held. When this occurs, the interrupt handling time is included in the spinlock holding time, and the spinlock holding time appears inordinately long. Xperf does not include spinlock events that are held while an interrupt is handled when calculating spinlock holding times. The `Events skipped due to interrupts` line displays the number of events that were not included in the calculation. This number is normally very small.


### Release functions

A spinlock can be acquired or released from different code paths. A list of release functions of the spinlock is displayed at the end of the report. The list is sorted by spinlock holding time. Additional information about a particular release function, such as acquisition or contention, is also presented.


## Example

The following example shows how to obtain a summary of spinlock data.

```
xperf -i example.etl -symbols -o example.txt -a spinlock -summary
```

The following example shows how to limit the number of records returned to the five most active spinlocks.

```
xperf -i example.etl -symbols -o example.txt -a spinlock -summary -counts 5
```


## Related topics

[spinlock](spinlock.md)

