---
title: Microsoft Store App Analysis
description: Microsoft Store App Analysis
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
Search.SourceType: Video
ms.assetid: 6643a13f-c164-4fc3-80e3-91ea2b7b8a80
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# Microsoft Store App Analysis


WPA now includes capabilities that help you analyze Microsoft Store app performance. Watch the video below for a quick overview of some of these features:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/bf588be3-5aa0-4679-9f00-7dcaa93df127?autoplay=false ]

## Microsoft Store App Profiles


WPA includes a set of profiles that help jumpstart your Microsoft Store app analysis. These profiles are contained in the **Profile Catalog** that can be found when you apply a profile to an open trace:

-   AppLaunch – Contains presets in a view that is geared for app launch analysis.

-   XAMLApplicationAnalysis – Contains all the presets and views necessary to get started with analyzing your XAML-based Microsoft Store app.

-   HTMLApplicationAnalysis – Contains all the presets and views necessary to get started with analyzing your HTML-based Microsoft Store app.

For more information about profiles, see [View Profiles](view-profiles.md).

For more information, including videos that get you started with the Microsoft Store app analysis profiles, see the following links:

-   [Big Picture](big-picture.md)

-   [Frame Analysis](frame-analysis.md)

## Attributed CPU Usage


In the **Attributed CPU Usage** graph, CPU usage is attributed to different activities. For example, one section of activity might be attributed to drawing content on the screen, while another section might be attributed to processing JavaScript code. These identifying tags help you to more easily identify how your app is spending time.

![regions of interest graph](images/acm-wpt-regions-1.png)

The Attributed CPU Usage graph contains the following presets that break down CPU usage in your Microsoft Store app:

-   DWM Thread CPU Breakdown

-   HTML Render Thread CPU Breakdown

-   HTML UI Thread CPU Breakdown

-   Known Thread CPU Breakdown

-   Utilization by Process, Thread, Activity

-   XAML Render Thread CPU Breakdown

-   XAML UI Thread CPU Breakdown

If you hover over the bars in the graph, you can see additional metadata for the corresponding activity.

In the **Attributed CPU Usage** table, the **Thread Name** column helps you quickly identify key threads in your app. In the screenshot below, you can see the **HTML UI Thread**, a named thread that does some work during the **Layout** activity:

![known thread cpu breakdown table](images/acm-wpt-regions-2.png)

**Warning**  
The **Attributed CPU Usage** table relies on regions of interest definitions to attribute CPU usage to different activities. When you use multiple regions files, different regions of interest can overlap and conflict. When these conflicts occur, WPA is unable to accurately attribute a single activity to a given thread in a given time range. To avoid these potential conflicts, use only one region definition file at a time.

 

## Thread Naming


Microsoft Store apps use different threads to do different types of work. For example, the XAML UI thread passes work to the render thread to draw to the screen. WPA uses descriptive thread names to clearly identify what the thread is doing. Knowing which of the many threads in your table is the render thread and which is the XAML UI thread allows you to look for particular patterns of behavior, especially between threads.

![descriptive thread names in wpa](images/acm-wpa-store-app-analysis-thread-names.png)

The image above shows activity from the XAML UI thread, the XAML Render thread, and the Desktop Window Manager (DWM) thread.

 

 






