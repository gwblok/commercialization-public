---
title: Explorer Initialization Duration
description: On/Off assessment results for the Explorer initialization transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Explorer Initialization Duration

**Most Applicable to:** Startup application developers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)

This metric captures the time from the end of the Winlogon phase until the Windows Shell (Explorer.exe) reports an initialized Start Screen. It includes the start of the userinit.exe process, which in turn starts Explorer.exe. It also includes the initiation of startup applications that are stored in **RunOnce** registry keys.

**Typical Influencing Factors**

In the absence of **RunOnce** applications, most of the time in this phase should be spent initializing the Explorer process. Explorer reads a number of libraries and data files into memory during its initialization process. Contending I/O from other running components can interfere with and delay this activity.

**Analysis and Remediation Steps**

Specific issues are usually generated for longer durations of the Explorer Initialization phase. You can gain more insight by opening WPA to the time interval of the Explorer Initialization activity. Avoid placing applications in the **RunOnce** key on a recurring basis because it delays Explorer Initialization.

Investigating specific issues during Explorer Initialization is beyond the scope of this document. For a list of common best practices, see [Best Practices for Time-Critical Tasks](results-for-the-onoff-assessments.md#best-practices-for-time-critical-tasks) in the [Results for the On/Off Assessments](results-for-the-onoff-assessments.md) topic.

