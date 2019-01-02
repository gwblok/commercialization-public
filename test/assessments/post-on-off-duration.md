---
title: Post On/Off Duration
description: On/Off assessment results for the Post On/Off transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Post On/Off Duration

**Most Applicable to:** Application developers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Boot Performance (Full Boot)
-   Standby Performance
-   Hibernate Performance

This metric measures the time from the completion of Post On/Off to the system being reasonably idle and responsive to user input. The goal of this phase is to bind and quantify background processing that continues after the Start Screen displays. This metric measures the duration of the Post On/Off phase, which represents the amount of time that is required for the system to accumulate 5 seconds of idle time. This time is accumulated by checking the CPU and storage utilization in 500ms time windows. If the cumulative time of both CPU and storage utilization is below 20%, the idle time of this window (500ms – max \[CPU time, Disk time\] in the window) is added to the total idle time until 5 seconds is reached. The metric reports this duration minus the 5 seconds of collected idle time.

> [!NOTE]
> Low-priority CPU and storage utilization times are ignored for these calculations.

Any software component that is running during this phase can affect the phase duration by performing disk I/O or computation.

**Detailed Sub-metrics**

No actual sub-metrics exist for this phase; however, because the phase duration is proportional to resource utilization, you can gain insight by examining processes that are running during this phase (expand **Processes per Phase** in Windows Assessment Console).

**Typical Influencing Factors**

Any software components that utilize CPU or storage resources during this phase can potentially contribute to the overall time. Additional startup applications usually have a negative impact on the Post On/Off phase.

In the Standby Performance and Hibernate Performance scenarios, which do not log off the user session, this phase is affected by applications that are running in the current workload.

**Analysis and Remediation Steps**

Identify processes that are consuming the most resources. You can do this either by expanding **Processes per Phase** in Windows Assessment Console or by looking at CPU and disk utilization graphs and summary tables in WPA. Issues are also likely to be generated for offending processes. See Looking at resource utilization metrics for more details.

To address the issue for the Boot Performance (Fast Startup) and Boot Performance (Full Boot) assessments, consider removing non-essential applications from the startup path or use the Task Scheduler to start these applications at a later time. If an application is critical for user logon (for example, it provides credential provider services or network services), make sure that the application is optimized for minimal resource consumption.

Avoid using managed code (CLR-based) startup applications because their initialization can activate the resource-costly initialization of .NET framework. This will further impact Post On/Off phase times and degrade user responsiveness.

