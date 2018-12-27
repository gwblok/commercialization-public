---
title: Flush Storage Volumes Duration
description: On/Off assessment results for the flush storage volumes transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Flush Storage Volumes Duration

**Most Applicable to:** Application developers, Windows service developers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Standby Performance
-   Hibernate Performance

This metric measures the time that the computer spends writing to the registry and saving any other modified pages to secondary storage.

**Typical Influencing Factors**

The time that this metric represents depends on the amount of data that needs to be flushed.

**Analysis and Remediation Steps**

Identifying the processes that are responsible for this data requires advanced analysis that is beyond the scope of this document; however, any process that writes large amounts of data directly before shutdown are suspect.

Examples are: an application that wrote a multi-megabyte data file by using cached I/O directly before exiting, or a service that modifies large amounts of file-mapped memory at shutdown time.

