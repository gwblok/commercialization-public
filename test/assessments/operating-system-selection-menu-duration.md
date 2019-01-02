---
title: Operating System Selection Menu Duration
description: On/Off assessment results for the OS selection menu transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Operating System Selection Menu Duration

**Most Applicable to:** System administrators

**Relevant Assessments:**

-   Boot Performance (Fast Startup)

This metric measures the time that it takes for the operating system selection menu to make its default selection. By default, a selection is made after 30 seconds (in the absence of user interaction).

**Typical Influencing Factors**

This metric is unaffected by system behavior. This metric is reported only on systems that have multiple operating systems installed, and it will always report 30 seconds if no user interaction is performed.

> [!NOTE]
> Although system behavior does not affect the duration of this metric, the boot process has many asynchronous processes that can run during this time. These processes can affect the results for activities that occur after the default selection is made, because some of the work that is normally performed during these times might already be completed.

**Analysis and Remediation Steps**

Remove all installed operating systems other except for the one that is being analyzed. To view the list of currently installed operating systems (including settings that affect this menu), run **msconfig.exe** at a command prompt and then choose the **Boot** tab.

