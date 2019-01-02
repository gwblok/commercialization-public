---
title: Boot Manager
description: On/Off assessment results for the boot manager transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Boot Manager

**Most Applicable to:** System administrators

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Boot Performance (Full Boot)
-   Hibernate Performance

This metric measures the time to find and start Winload.exe, the operating system loader, on the Windows boot partition.

**Typical Influencing Factors**

This metric can be affected by BitLocker operations, especially if a PIN is required for BitLocker to start.

**Analysis and Remediation Steps**

Use a BitLocker unlock method that does not require manual PIN entry.

