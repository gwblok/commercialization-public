---
title: Suspend Services Duration
description: On/Off assessment results for the suspend services transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Suspend Services Duration

**Most Applicable to:** Windows service developers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Standby Performance
-   Hibernate Performance

This metric measures the time that the computer spends notifying services of the impending power state change. All services that register to receive power management events (SERVICE\_ACCEPT\_POWEREVENT) receive suspend notifications. Because these notifications are sent serially, any delay in a service directly contributes to the overall shutdown/suspend duration. A 30 second timeout is enforced (on a per-service basis) to process this notification; after this timeout, the system moves on to the next phase. Because registering for this notification is optional, no specific action by the service is required by the OS.

**Detailed Sub-metrics**

When the metric is expanded, a more detailed phase view is presented with a list of individual services and their corresponding durations.

**Typical Influencing Factors**

This metric captures the cumulative time that all services take to respond to a power query. This metric can be affected by a single process that takes too long, in addition to the cumulative time of all process responses.

Most services are not required to do any significant work in response to standby and hibernate power notifications. From a service’s perspective, fast startup is similar to hibernate.

**Analysis and Remediation Steps**

Identify a service that significantly impacts this metric. Longer delays in service responses generally produce issues that are specific to a given service. When such an issue is generated, you can follow the link inside the issue to see advanced issue details. When an issue is not generated, subsequent analysis in WPA is required. This additional analysis is beyond the scope of this document. For more information about common best practices, see [Best Practices for Time-Critical Tasks](results-for-the-onoff-assessments.md#best-practices-for-time-critical-tasks) in the [Results for the On/Off Assessments](results-for-the-onoff-assessments.md) topic.

**Additional Information**

[MSDN: OnNow/ACPI Support](http://go.microsoft.com/fwlink/?LinkId=247504)

