---
title: Windows Performance Toolkit
description: Included in the Windows Assessment and Deployment Kit, the Windows Performance Toolkit consists of performance monitoring tools that produce in-depth performance profiles of Windows operating systems and applications.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ef3d3649-4d0e-4207-833c-f58130aca12f
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# Windows Performance Toolkit

Included in the [Windows Assessment and Deployment Kit](http://aka.ms/adk), the Windows Performance Toolkit consists of performance monitoring tools that produce in-depth performance profiles of Windows operating systems and applications. This documentation discusses both Windows Performance Recorder (WPR) and Windows Performance Analyzer (WPA).

## Windows Performance Toolkit components

The Windows Performance Toolkit consists of two independent tools: Windows Performance Recorder (WPR) and Windows Performance Analyzer (WPA). In addition, support is maintained for the previous command-line tool, Xperf. However, Xperfview is no longer supported. All recordings must be opened and analyzed by using WPA.

The following are the system requirements for running Windows Performance Toolkit:

- Windows Performance Recorder (WPR): Windows 8 or later.

- Windows Performance Analyzer (WPA): Windows 8 or later with the Microsoft .NET Framework 4.5 or later.

### Windows Performance Recorder

WPR is a powerful recording tool that creates Event Tracing for Windows (ETW) recordings. You can run WPR from the user interface (UI) or from the command line. WPR provides built-in profiles that you can use to select the events that are to be recorded. Alternatively, you can author custom profiles in XML. WPR can also be invoked and controlled by using the **WPRControl** application programming interface (API). For more information about the WPRControl API, see [WPRControl API Reference](http://go.microsoft.com/fwlink/p/?linkid=223235).

For basic procedures and a detailed walkthrough, see the [WPR Quick Start](wpr-quick-start.md). For complete documentation of the WPR UI, see [WPR Features](http://go.microsoft.com/fwlink/p/?linkid=223236). For reference of command-line options, see [WPR Command-Line Options](http://go.microsoft.com/fwlink/p/?linkid=223233). For step-by-step procedures, see [WPR How-to Topics](http://go.microsoft.com/fwlink/p/?linkid=223237). For discussion of key scenarios, see [WPR Scenarios](windows-performance-recorder-common-scenarios.md). For complete reference material, including a recording profile XML reference and a legacy Xperf reference, see [WPR Reference](http://go.microsoft.com/fwlink/p/?linkid=223245).

### Windows Performance Analyzer

WPA is a powerful analysis tool that combines a very flexible UI with extensive graphing capabilities and data tables that can be pivoted and that have full text search capabilities. WPA provides an **Issues** window to explore the root cause of any identified.

For basic procedures and a detailed walkthrough, see the [WPA Quick Start Guide](wpa-quick-start-guide.md). For complete documentation of the WPR UI, see [WPA Features](http://go.microsoft.com/fwlink/p/?linkid=223251). For step-by-step procedures, see [WPA How-to topics](http://go.microsoft.com/fwlink/p/?linkid=223252). For extended discussion of key scenarios, see [WPA Scenarios](windows-performance-analyzer-common-scenarios.md).

## Contents

|Section|Description|
|----|----|
|[What's New in the Windows Performance Toolkit](whats-new-in-the-windows-performance-toolkit.md)|Describes the new features available in this release.|
|[Windows Performance Recorder](windows-performance-recorder.md)|Provides complete documentation for WPR. On MSDN, this includes a complete command-line and Extensible Markup Language (XML) reference.|
|[Xperf Command-Line Reference](xperf-command-line-reference.md)|Gives complete reference material for Xperf.|
|[Kernel Trace Control API Reference](kernel-trace-control-api-reference.md)|Covers the Kernel Trace Control API, an extension of the ETA Event Tracing API that is supported for backward compatibility with existing scripts and profiles.|
|[Windows Performance Analyzer](windows-performance-analyzer.md)|Provides complete documentation for WPA to enable you to analyze recordings created with WPR or from the Assessment Platform.|
|[Windows Performance Step-by-Step Guides](windows-performance-step-by-step-guides.md)|Provides instructions for performing labs that address common performance scenarios.|
