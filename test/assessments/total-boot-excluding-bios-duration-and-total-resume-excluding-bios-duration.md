---
title: Total Boot (Excluding BIOS) Duration & Total Resume (Excluding BIOS) Duration
description: On/Off assessment results for the total boot (excluding BIOS) & total resume (excluding BIOS) transition phases


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Total Boot (Excluding BIOS) Duration & Total Resume (Excluding BIOS) Duration

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Boot Performance (Full Boot)
-   Standby Performance
-   Hibernate Performance

This metric measures the time that the computer spends starting up. This metric captures the time from the end of [BIOS Initialization](bios-initialization-duration.md) to the end of the [Post On/Off](post-on-off-duration.md) phase, which ends when the system reaches an idle state.

**Detailed Sub-metrics**

When the metric is expanded, a list of boot/resume sub-phases is presented.

> [!NOTE]
> Durations of the sub-phases do not necessarily equal the overall duration.

**Typical Influencing Factors**

This metric is an overall metric for system boot/resume, and it can be affected by any software components that run on the boot/resume path.

**Analysis and Remediation Steps**

Expand this metric to see the sub-metrics that provide more information on individual sub-phases. Examine individual sub-phase metrics and issues to find potential delay contributors.

