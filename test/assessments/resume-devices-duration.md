---
title: Resume Devices Duration
description: On/Off assessment results for the resume devices transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Resume Devices Duration

**Most Applicable to:** Driver developers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Standby Performance
-   Hibernate Performance

During shutdown/suspend, every device driver is sent a power (IRP\_MJ\_POWER) IRP that has an IRP\_MN\_SET\_POWER minor code and working power state. Device drivers subsequently send Device Power IRPs to corresponding devices. This metric measures the time for all drivers to process the set power IRP.

> [!NOTE]
> Drivers should not retain the System Power IRP during this phase. Each driver can delay system startup by not promptly handling the system power IRP.

**Detailed Sub-metrics**

When the metric is expanded, a more detailed phase view is presented with a list of devices and their corresponding durations.

**Typical Influencing Factors**

This metric captures the cumulative time that all drivers take to respond to an IRP\_MN\_SET\_POWER power request. This metric can be affected by a single driver that takes too much time, in addition to the cumulative time of all driver responses.

> [!NOTE]
> If a driver owns a power policy for a device, it generates a Device Power IRP in response to receiving a System Power IRP. Drivers should not wait to complete the System IRP until the Device IRP is completed because that wait can prevent other devices from receiving their System IRPs. This series of waits cause serialization delays and increases the overall suspend time.

**Analysis and Remediation Steps**

You can identify a driver or drivers that significantly impact this metric by looking at the sub-metrics. Long delays in the driver responses usually produce issues that are specific to a given driver. When such an issue is generated, follow the link inside the issue to see advanced issue details. When an issue is not generated, subsequent analysis in WPA is required; this is beyond the scope of this document. See [Best Practices for Time-Critical Tasks](results-for-the-onoff-assessments.md#best-practices-for-time-critical-tasks) in the [Results for the On/Off Assessments](results-for-the-onoff-assessments.md) topic.

**Additional Information**

[MSDN: IRP\_MN\_SET\_POWER](http://go.microsoft.com/fwlink/?LinkId=247508)

