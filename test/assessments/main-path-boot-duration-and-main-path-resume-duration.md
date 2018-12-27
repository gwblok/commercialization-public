---
title: Main Path Boot Duration & Main Path Resume Duration
description: On/Off assessment results for the main path boot & main path resume transition phases


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Main Path Boot Duration & Main Path Resume Duration

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Boot Performance (Full Boot)
-   Standby Performance
-   Hibernate Performance

This metric measures the time from when the computer begins start-up until the user’s Desktop is visible. This metric captures the time from the end of [BIOS Initialization](bios-initialization-duration.md) until the Windows 8 UI is shown, and it does not include the [Post On/Off](post-on-off-duration.md) phase.

**Detailed Sub-metrics**

When the metric is expanded, a list of sub-phases (excluding the Post On/Off phase) is presented.

> [!NOTE]
> Durations of the sub-phases do not necessarily equal the overall duration.

**Typical Influencing Factors**

This metric is an overall metric for boot/resume to a visible Desktop. It can be affected by any software components that run before the Desktop displays.

**Analysis and Remediation Steps**

Expand this metric to see the sub-metrics that provide more information on individual sub-phases. Examine individual sub-phase metrics and issues to find potential delay contributors.

