---
title: Results for the On/Off Assessments
description: Results for the On/Off Assessments
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7aa9fcbc-4019-4be0-829a-d50eadc6ca02
ms.mktglfcycl: plan
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# Results for the On/Off Assessments

This topic helps you interpret the results produced by the On/Off assessments (Boot Performance (Fast Startup), Boot Performance (Full Boot), Standby Performance, and Hibernate Performance). It also provides guidance on how to use the results to identify and resolve several common issues that negatively impact the end user’s experience when shutting down and booting a computer.

For more information about On/Off Transition assessments, see [On/Off Transition Performance](onoff-transition-performance.md).


## Goals File

You can create custom goals to measure your improvements in the Results View. Goals files are a triage tool that can help you understand how a PC is performing and to compare PCs in your business.

For example, goals for a basic laptop might be different than the goals you set for a high end desktop computer, or market expectations might change in such a way that you want the flexibility to define different goals and key requirements as time passes and technology improves.

When a metric value is compared to the goal for that metric, the status is color coded in the Result View as follows:

-   Light purple means that the system has a great user experience and that there are no perceived problems.

-   Medium purple means that the user experience is tolerable and you can optimize the system. Review the recommendations and analysis to see what improvements can be made to the system. These can be software changes, configuration changes or hardware changes.

-   Dark purple means that the system has a poor user experience and that there is significant room for improvements. Review the recommendations and analysis to see the improvements that can be made to the system. These can be software changes, configuration changes or hardware changes. You might have to consider making tradeoffs to deliver a high quality Windows experience.

-   No color means that there are no goals defined for the metric.

> [!NOTE]
> In the Windows Assessment Toolkit for Windows 8, some assessments include default goals files. The first time you view results using this version of the tools, the default goals file is used. However, you can also define custom goals for Windows 8 the same way that you can for Windows 8.1 and Windows 10.

You can set the goals file location and add a goals file to that location before you can use the UI to apply the custom goals. Once a goals file is selected it will continue to be the goals file that is used for any results that are opened.

Only one goals file can be used at a time. Goals for all assessments are set in a single goals file. The assessment tools will search for goals in the following order:

1.  A custom goals file
2.  Goals that are defined in the results file
3.  Goals that are defined in the assessment manifest

You can use the sample goals file that is provided at %PROGRAMFILES%\\Windows Kits\\10\\Assessment and Deployment Kit\\Windows Assessment Toolkit\\SDK\\Samples\\Goals to create your own goals file.

> [!NOTE]
> You cannot package a goals file with a job, but you can store it on a share for others to use.


## Metrics

This section describes the key metrics reported by the On/Off assessments, common causes of poor results for these metrics, and common remediation for issues related to these metrics. This section also helps you identify the audience for which the metric is most applicable.

The following table describes the metrics that may be available in an assessment:

| Assessment                                 | Metric Description                                                                                                                                              |
| :----------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Boot Performance (Fast Startup) Assessment | This metric captures the time from the start of the shutdown phase, to the end of writing the hiberfile to disk and the transition to a lower power state (S4). |
| Boot Performance (Full Boot) Assessment    | This metric captures the time from the start of the shutdown phase to the transition to a powered off state.                                                    |
| Standby Performance Assessment             | This metric captures the time from the start of the suspend phase to the transition to a lower power state (S3).                                                |
| Hibernate Performance Assessment           | This metric captures the time from hibernate to the end of writing the hiberfile to disk and the transition to a lower power state (S4).                        |

You can view On/Off assessment metrics for the following transition phases:

-   [BIOS Initialization Duration](bios-initialization-duration.md)
-   [Boot Manager](boot-manager.md)
-   [Explorer Initialization Duration](explorer-initialization-duration.md)
-   [Flush Storage Volumes Duration](flush-storage-volumes-duration.md)
-   [Hiberfile Read Duration](hiberfile-read-duration.md)
-   [Hiberfile Write Duration](hiberfile-write-duration.md)
-   [Main Path Boot Duration & Main Path Resume Duration](main-path-boot-duration-and-main-path-resume-duration.md)
-   [Operating System Selection Menu Duration](operating-system-selection-menu-duration.md)
-   [Post On/Off Duration](post-on-off-duration.md)
-   [Query Devices Duration](query-devices-duration.md)
-   [Resume Devices Duration](resume-devices-duration.md)
-   [Shutdown Duration & Suspend Duration](shutdown-duration-and-suspend-duration.md)
-   [Shutdown Processes Duration](shutdown-processes-duration.md)
-   [Superfetch Prepare Memory Duration](superfetch-prepare-memory-duration.md)
-   [Suspend Devices Duration](suspend-devices-duration.md)
-   [Suspend Processes Duration](suspend-processes-duration.md)
-   [Suspend Services Duration](suspend-services-duration.md)
-   [Total Boot (Excluding BIOS) Duration & Total Resume (Excluding BIOS) Duration](total-boot-excluding-bios-duration-and-total-resume-excluding-bios-duration.md)
-   [User Session Shutdown Duration](user-session-shutdown-duration.md)
-   [Winlogon Resume Duration](winlogon-resume-duration.md)
-   [Winlogon Suspend Duration & Winlogon Notifications Duration](winlogon-suspend-duration-and-winlogon-notifications-duration.md)

> [!NOTE]
> If you enabled the Enable Minifilter Diagnostic Mode setting, the assessment results will include minifilter metrics. For more information about minifilter metrics and results, see [Minifilter Diagnostics](minifilter-diagnostics.md).


## Issues

The On/Off Transition Performance assessments perform advanced issue analysis and provide links to WPA to troubleshoot the issues that the assessment has identified. When WPA opens, additional details about disk activity or CPU activity might be available, depending on the type of issue. This section describes common investigative techniques that you can use to analyze performance issues.

**Find the Largest Contributor**

Open the assessment results file in Windows Assessment Console and expand the corresponding parent metric. The child sub-metrics typically provide information on specific components that affect the parent metric.

For example, consider the [Shutdown Processes Duration](shutdown-processes-duration.md) metric. You can expand the metric to view three sub-metric tables for this phase. The first two tables show the CPU and disk utilization, and the third table shows the durations of individual processes that are being shut down.

Additional columns, such as the **Detail** column, provide more details for the sub-metrics. In **User Session Shutdown Processes**, the **Detail** column shows a PID.

> [!NOTE]
> In the default view, the **Detail** column might contain the value “Various” because PIDs cannot be aggregated across iterations. Expand iterations to see individual PIDs.

Windows Assessment Console allows you to sort the sub-metrics list by any data column (except for the top level Fast Startup phase lists, which are sorted by phase order during shutdown/boot).

For example, in the expanded process list for the [User Session Shutdown Processes](user-session-shutdown-duration.md) phase, right-click the table header and then choose **Sort rows descending**.

You can use this technique for multiple top level phase durations.

**Look at Resource Utilization Metrics**

View the detailed resource utilization metrics for each process during this phase. To retrieve this information, expand the processes for each phase tab in the section, and then sort by either CPU usage or total disk usage.

**Additional Information**

For more information about in-depth analysis issues and recommendations, see [Common In-Depth Analysis Issues](common-in-depth-analysis-issues.md).


### The assessment reports an exit code of 0x80050006

This error occurs when maintenance tasks have been registered on the PC but have not completed before the assessment run. This prevents the assessment from running, as maintenance tasks often impact assessment metrics.

To resolve this issue, do one of the following:

1.  Ensure that the computer is connected to a network and is running on AC power. Manually initiate pending maintenance tasks with the following command from an elevated prompt:

    `rundll32.exe advapi32.dll,ProcessIdleTasks`

2.  Disable regular and idle maintenance tasks, and stop all maintenance tasks before running the assessment.


## Best Practices for Time-Critical Tasks

If you don’t want a task to be delayed, ensure it does not do anything which takes a long time. Below are some things to avoid.

-   If a time-critical response is required, for example, to process the WM\_ENDSESSION during shutdown, do not plan on doing any substantial work when receiving the request (aside from data reliability work like saving user modifications, which must be done).

-   Avoid performing any operations which might take a longer time, unless absolutely necessary. Defer them until the current time-critical task is complete. Avoid any APIs which contain the warning: “beware of performance considerations when using this API”.

-   Avoid any network dependencies because any network request can be delayed by network issues. This is especially true for Startup and Shutdown scenarios since the network is not guaranteed to be available for the entire time.

-   Avoid long timeouts. If a wait is required, ensure the wait time is reasonably bound by a small (in the context of the time critical task in question) timeout value.

-   Avoid excessive computation. Keep in mind that processors vary in speed so a computation taking 100ms on a very fast computer might end up taking seconds on a slower one.

-   Avoid unnecessary storage I/O. Any I/O request could be delayed by other components. At any time there are dozens of application and services running on a typical system and the storage resources are limited. Your I/O request might get queued behind hundreds of similar requests from other components.

-   Avoid disk flushes, for example, those initiated through calling FlushFileBuffers API. Flushing causes the disk stack to delete its caches and is supposed to force the hard drive to write out data in its RAM buffers. Typically, this operation is very costly and does not guarantee data consistency since the hard drives often ignore the request.

-   Avoid flushing registry hives by calling RegFlushKey API. Because of registry design, the API is causing modified data for the entire hive to be flushed to disk, which is a very costly operation. Flushing registry keys is an action that is not typically needed since the operating system provides a consistent registry view to all the components. Also, the registry itself does asynchronous flushes every several seconds.

-   Avoid opening new RPC connections since the RPC authentication process is costly. Establishing a new RPC connection involves costly security checks.

-   Avoid calling transactional APIs such as TxF APIs as they commonly perform a number of costly operations for each API call. These APIs obtain reliability at the cost of performance, so these APIs should not be used during time-critical tasks.


## Related topics

[Assessments](assessments.md)

[On/Off Transition Performance](onoff-transition-performance.md)

[Automate reboots before you run an assessment](automate-reboots-before-you-run-an-assessment.md)

[Windows Assessment Toolkit](index.md)

