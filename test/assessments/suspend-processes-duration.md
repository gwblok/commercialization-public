---
title: Suspend Processes Duration
description: On/Off assessment results for the suspend processes transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Suspend Processes Duration

**Most Applicable to:** Application developers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Standby Performance
-   Hibernate Performance

This metric measures the time that the computer spends notifying processes of the impending power state change.

During this phase, the Client/Server Runtime Server Subsystem (Csrss.exe) broadcasts WM\_POWERBROADCAST window messages together with the event type of PBT\_APMSUSPEND to every application that owns a window. The system might also power off the monitor.

This activity can be seen in the WPA **Activities** graph as a large gap between consecutive processes that are being suspended. One second or more is expected to power off the monitor. This is a necessary stage during suspend/shut down, and it should not be considered a performance bottleneck for this metric.

Look at the **CPU Usage (Sampled)** graph during this time to show CPU utilization in the csrss.exe process on the following stack:

```
[Root] (csrss.exe) 
winsrv.dll!RegisterForDeviceBroadcastNotifications 
|- winsrv.dll!ZwUserCallNoParam 
|    win32k.sys!xxxUserPowerStateCalloutWorker 
|    |- win32k.sys!PowerOffMonitor 
|    |    |- win32k.sys!FadeDesktop 
|    |    |- win32k.sys!DrvSetMonitorPowerState 
|    |    |- win32k.sys!UpdateDisplayState 
|    |    |- win32k.sys!DwmSyncClearSwapChain 
|    |    |- win32k.sys!RestoreGammaRamp
```

Gaps in **Suspend Processes** because of CPU consumption on other stacks, or delays without CPU utilization on the current stack, can suggest areas to investigate further.

When the metric is expanded, a more detailed phase view is presented, with a set of sub-metrics that measure the times that each process took to respond to suspend notifications. The columns show the following information:

-   A PID by iteration in the **Detail** column. In the default view, this column might contain the value “Various” because PIDs cannot be aggregated across iterations. Expand iterations to see individual PIDs.

-   The time that this particular process took during this phase.

> [!NOTE]
> If an application has more than one window, the same process can receive more than one notification.

**Typical Influencing Factors**

Each application has the ability to delay system shutdown by delaying its response to the WM\_POWERBROADCAST message with PBT\_APMSUSPEND event type. Because this metric captures the cumulative time that all windows GUI processes take to respond to the suspend notification, this metric can be affected by a single process that takes too long, in addition to a cumulative time of all process responses. Note that the process must be running to impact this metric; because the Boot Performance (Fast Startup) assessment reboots before it collects data for analysis, these processes come almost exclusively from startup applications or scheduled tasks.

**Analysis and Remediation Steps**

Identify the processes that most significantly impact this metric. In Windows Assessment Console, expand the **Suspend Processes Duration** metric to get the details for this phase. In the **Process** list for this phase, sort the **Duration** in descending order and look for the largest contributors.

If possible, remove applications from the startup path. As a best practice, startup applications should be kept to a minimum. If an unessential application is causing delays, consider removing it from the list of startup applications.

Troubleshooting and fixing issues with that significantly impact the startup path requires deep analysis of application delays. See [Best Practices for Time-Critical Tasks](results-for-the-onoff-assessments.md#best-practices-for-time-critical-tasks) in the [Results for the On/Off Assessments](results-for-the-onoff-assessments.md) topic for a list of common best practices.

**Additional Information**

[MSDN: PBT\_APMSUSPEND event](http://go.microsoft.com/fwlink/?LinkId=247503)

