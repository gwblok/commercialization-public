---
title: Hiberfile Write Duration
description: On/Off assessment results for the hiberfile write transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Hiberfile Write Duration

**Most Applicable to:** Application developers, Windows service developers, Driver developers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Hibernate Performance

This metric measures the time that the system spends writing the relevant contents of main memory to secondary storage; specifically, into hiberfile.sys file that is usually found in the root directory of the system drive.

**Detailed Sub-metrics**

When the metric is expanded, the size of the hiberfile is shown in Kilobytes.

**Typical Influencing Factors**

The time it takes to write the hiberfile is directly proportional to the amount of data that needs to be written. This data consists of memory that is in use by the operating system, drivers, and services, in addition to any data that the system must read during system resume (as identified during the [Superfetch Prepare Memory](superfetch-prepare-memory-duration.md) phase).

A driver that uses large amounts of memory can influence this metric by having the memory manager write data into the hiberfile. Or, a startup application can cause large amounts of data to be read on the resume path. In these cases, the Superfetch service ensures that data is included into the hiberfile to avoid slow random faulting on the resume path.

> [!NOTE]
> Hard drive physical performance characteristics, such as sequential write throughput, also affects this metric.

**Analysis and Remediation Steps**

Identifying the specific components that contribute to the longer hiberfile write durations requires detailed memory analysis and is beyond the scope of this document. However, each running driver and service can contribute to this metric by retaining large memory allocations. The number and footprint of the startup applications, and of other components that read data during startup, can also influence this metric.

