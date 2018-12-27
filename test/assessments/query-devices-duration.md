---
title: Query Devices Duration
description: On/Off assessment results for the query devices transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Query Devices Duration

**Most Applicable to:** Driver developers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Standby Performance
-   Hibernate Performance

During the shutdown/suspend phase, every device driver is sent a power IRP that has a IRP\_MN\_QUERY\_POWER minor code and a power state (S4 for Boot Performance (Fast Startup)/Hibernate Performance, S3 for Standby Performance). This metric measures the duration of all drivers that process the query power IRP.

Each driver can delay system shutdown by not promptly handling the IRP.

**Detailed Sub-metrics**

When the metric is expanded, a more detailed phase view is presented with a list of devices and their corresponding durations.

**Typical Influencing Factors**

This metric captures the cumulative time that all drivers take to respond to power queries. This metric can be affected by a single driver that takes too long to respond, in addition to the cumulative time of all driver responses.

**Analysis and Remediation Steps**

You can identify a driver or drivers that significantly impact this metric by looking at the sub-metrics. Longer delays in the driver response durations usually produce issues that are specific to a given driver. When such an issue is generated, follow the link inside the issue to see advanced issue details. When an issue is not generated, subsequent analysis in WPA is required; this is beyond the scope of this document. See [Best Practices for Time-Critical Tasks](results-for-the-onoff-assessments.md#best-practices-for-time-critical-tasks) in the [Results for the On/Off Assessments](results-for-the-onoff-assessments.md) topic for a list of common best practices.

> [!NOTE]
> If a driver owns a power policy for a device, it generates a Device Power IRP in response to receiving a System Power IRP. Drivers should not wait to complete the System IRP until the Device IRP is completed because that wait can prevent other devices from receiving their System IRPs. This series of waits cause serialization delays and increases the overall suspend time.

**Additional Information**

[MSDN: IRP\_MN\_QUERY\_POWER](http://go.microsoft.com/fwlink/?LinkId=247506)

