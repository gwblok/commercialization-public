---
title: Shutdown Processes Duration
description: On/Off assessment results for the shutdown processes transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Shutdown Processes Duration

**Most Applicable to:** Application developers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)

When the assessment initiates the user session shutdown, each UI thread in every Graphical User Interface (GUI) application is sent a WM\_QUERYENDSESSION message. After Windows receives a response to the WM\_QUERYENDSESSION message, Windows sends the WM\_ENDSESSION to the same threads. If after 5 seconds any application has not responded to these notifications, Windows terminates the application. Any application can delay system shutdown by not promptly responding to the messages.

> [!NOTE]
> If a user initiates the shutdown, a user dialog box displays after the timeout expires. This dialog shows information about the application that is blocking the shutdown, and allows the user to **Force** or **Cancel** the shutdown.

This metric measures the time that the computer spends shutting down all processes in the user session.

**Detailed Sub-metrics**

When the metric is expanded, a more detailed view is presented of a set of sub-metrics that measure times each individual process took to respond to shutdown notifications. The columns show the following information:

-   A PID by iteration in the Detail column. In the default view, this column might contain the value “Various” because PIDs cannot be aggregated across iterations. Expand iterations to see individual PIDs.

-   The time that this particular process took during this phase.

**Typical Influencing Factors**

This metric captures the cumulative time of all running processes that have UI threads to respond to shutdown notification. This metric can be affected by a single process that takes too long, in addition to the cumulative time of all process responses.

Each process that has a UI thread can delay system shutdown by delaying its response to the WM\_QUERYENDSESSION message or WM\_ENDSESSION message.

> [!NOTE]
> To impact this metric, a process must be running. Because this assessment reboots before it collects data for analysis, the running processes are almost exclusively from startup applications or scheduled tasks.

**Analysis and Remediation Steps**

You can identify processes that most significantly impact this metric by using the [Find the Largest Contributor](results-for-the-onoff-assessments.md#issues) technique in the [Results for the On/Off Assessments](results-for-the-onoff-assessments.md) topic.

If possible, remove applications from the startup path. Because the assessment reboots before it performs measurements, the only applications that are running at shutdown are the applications that began at startup. As a best practice, startup applications should be kept to a minimum. If an unessential application is causing delays, consider removing it from the list of startup applications.

Find the possible reasons that responses to WM\_QUERYENDSESSION message or WM\_ENDSESSION can be delayed, and troubleshoot and fix the underlying issues. See [Best Practices for Time-Critical Tasks](results-for-the-onoff-assessments.md#best-practices-for-time-critical-tasks) in the [Results for the On/Off Assessments](results-for-the-onoff-assessments.md) topic for a list of common best practices.

**Additional Information**

[MSDN: WM\_QUERYENDSESSION message](http://go.microsoft.com/fwlink/?LinkId=247501)

[MSDN: WM\_ENDSESSION message](http://go.microsoft.com/fwlink/?LinkId=247502)

