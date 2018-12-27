---
title: Hiberfile Read Duration
description: On/Off assessment results for the hiberfile read transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Hiberfile Read Duration

**Most Applicable to:** Application developers, Windows service developers, driver developers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Hibernate Performance

This metric measures the time that the system spends reading the contents of the hiberfile into main memory.

**Detailed Sub-metrics**

When the metric is expanded, the size of the hiberfile (in Kilobytes) is shown.

**Typical Influencing Factors**

The time that it takes to read the hiberfile is directly proportional to the amount of data that must be read. This data consists of data in memory that is used by the operating system, drivers, and services, in addition to data that the system uses for system resume (identified during the [Superfetch Prepare Memory](superfetch-prepare-memory-duration.md) phase of shutdown/suspend).

> [!NOTE]
> Hard drive physical performance characteristics, such as sequential read throughput, also affects this metric.

**Analysis and Remediation Steps**

Identifying the specific components that contribute to longer hiberfile read durations requires detailed memory analysis and is beyond the scope of this document.

> [!NOTE]
> Each running driver and service can contribute to this metric by retaining large memory allocations. The number and footprint of startup applications and other components that read data during startup also influence this metric.

