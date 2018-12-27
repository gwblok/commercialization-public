---
title: User Session Shutdown Duration
description: On/Off assessment results for the user session shutdown transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# User Session Shutdown Duration

**Relevant Assessments:**

-   Boot Performance (Fast Startup)

This metric measures the time that the computer spends shutting down the user session. This phase includes shutting down user-session processes, logging the user off, and notifying subscribers to Winlogon notifications. When the metric is expanded, a list of shutdown or suspend sub-phases is presented.

> [!NOTE]
> The durations of the sub-phases do not necessarily add up to the overall duration.

This metric is an overall metric for the system shutdown. It can be affected by any software components that are running on the shutdown path.

**Analysis and Remediation Steps**

Expand this metric to see the sub-metrics that provide more information on individual sub-phases of shutdown. Examine individual sub-phase metrics and issues to find potential delay contributors.

