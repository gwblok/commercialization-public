---
title: Suspend Devices Duration
description: On/Off assessment results for the suspend devices transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Suspend Devices Duration

**Most Applicable to:** Driver developers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Standby Performance
-   Hibernate Performance

During the shutdown phase of the Boot Performance (Fast Startup) scenario, every device driver is sent a power (IRP\_MJ\_POWER) I/O (IRP that has IRP\_MN\_SET\_POWER minor code and a power state (S4 for Boot Performance (Fast Startup) or Hibernate Performance, S3 for Standby Performance).

This metric measures the time that is required for all drivers to process the set power IRP.

When device drivers process this IRP, they save appropriate device context (if required), and put the device in the appropriate state for sleep or hibernate. Each driver can delay system shutdown by not promptly handling the IRP.

**Detailed Sub-metrics**

When the metric is expanded, a more detailed phase view is presented that includes a list of devices and their corresponding durations.

**Typical Influencing Factors**

This metric captures the cumulative time that all drivers take to respond to a power query. This metric can be affected by a single driver that takes too long to respond in addition to the cumulative time of all responses.

> [!NOTE]
> If a driver owns a power policy for a device, it generates a Device Power IRP in response to receiving a System Power IRP. Drivers should not wait to complete the System IRP until the Device IRP is completed because that wait can prevent other devices from receiving their System IRPs. This series of waits cause serialization delays and increases the overall suspend time.

**Analysis and Remediation Steps**

You can identify a driver or drivers that significantly impact this metric by looking at the sub-metrics. Long delays in the driver response durations usually produce issues that are specific to a given driver. When such an issue is generated, follow the link inside the issue to see advanced issue details. When an issue is not generated, subsequent analysis in WPA is required; this kind of analysis is beyond the scope of this document.

**Additional Information**

[MSDN: IRP\_MN\_SET\_POWER](http://go.microsoft.com/fwlink/?LinkId=247508)

