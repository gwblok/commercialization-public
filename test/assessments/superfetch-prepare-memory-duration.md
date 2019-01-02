---
title: Superfetch Prepare Memory Duration
description: On/Off assessment results for the superfetch prepare memory transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Superfetch Prepare Memory Duration

**Most Applicable to:** Application developers, Windows service developers

**Relevant Assessments**

-   Boot Performance (Fast Startup)
-   Standby Performance
-   Hibernate Performance

This metric measures the time that the Windows Superfetch service spends preparing the memory state for the subsequent boot/resume. Superfetch pre-fetches data that is frequently accessed on startup, and stores it either in the hiberfile (for Boot Performance (Fast Startup) and Hibernate Performance) or main memory (Standby Performance) to avoid excessive disk accesses on resume. This feature accelerates the resume process.

**Typical Influencing Factors**

During this phase, the Superfetch service accesses data that is read during startup. The duration of this phase is directly influenced by the amount of data that must be read during startup by startup applications, services, credential providers, and so on.

**Analysis and Remediation Steps**

This phase requires advanced analysis that is not included in this document.

