---
title: BIOS Initialization Duration
description: On/Off assessment results for the BIOS initialization transition phase


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# BIOS Initialization Duration

**Most Applicable to:** BIOS manufacturers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Boot Performance (Full Boot)
-   Standby Performance
-   Hibernate Performance

This metric measures the time that the platform firmware spends identifying and initializing hardware devices and running a power-on self-test (POST).

> [!NOTE]
> BIOS initialization happens before the operating system receives control. The assessment cannot thoroughly inspect the phase and can only report on its duration.

**Detailed Sub-metrics**

Boot Performance (Fast Startup) is the only scenario to provide additional sub-metrics for this metric. For systems that contain BIOS that support the latest Advanced Configuration and Power Interface (ACPI) standard (ACPI 5.0), this metric can be expanded to show the POST time that is reported by the Firmware Performance Data Table (FPDT). This is an alternate measurement for the BIOS Initialization duration, which is reported by kernel instrumentation.

**Typical Influencing Factors**

The boot order that is set for the system can be a significant source of delay during BIOS Initialization. This order can require the system to check for bootable optical, floppy, USB, or other hard drives before it loads Windows. PXE Boot (network/remote boot) can also be set as part of the boot order; if this is enabled, it can significantly affect the delay. Some BIOS configurations also have advanced diagnostics or verification modes that can take longer to complete.

**Analysis and Remediation Steps**

No additional information is captured for the BIOS phase. Typical influencing factors such as enabled PXE boot should be checked. The BIOS manufacturer should be consulted when you need to triage or alter these settings. A deeper investigation of the BIOS Initialization phase is beyond the scope of this document.

