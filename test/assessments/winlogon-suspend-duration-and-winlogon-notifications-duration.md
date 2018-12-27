---
title: Winlogon Suspend Duration & Winlogon Notifications Duration
description: On/Off assessment results for the Winlogon suspend & Winlogon notifications transition phases


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Winlogon Suspend Duration & Winlogon Notifications Duration

**Most Applicable to:** Winlogon subscriber developers, group policy script owners, system administrators

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Boot Performance (Full Boot)
-   Standby Performance
-   Hibernate Performance

This metric measures the time that is spent by Winlogon, including time spent performing subscriber notifications/callbacks.

For the Boot Performance (Fast Startup) scenario, the **Winlogon Notifications** metric in Windows Assessment Console reflects the cumulative time that is spent processing all Winlogon subscriber notifications and callbacks. However, to provide context in the Windows® Performance Analyzer (WPA) timeline, the **Winlogon Notifications** activity starts with the first subscriber notification/callback and ends with the last. The time that is spent processing each notification is represented by individual child activities.

Boot Performance (Fast Startup) is the only assessment that provides additional sub-metrics for this metric. During suspend, Winlogon issues synchronous subscriber notifications to registered subscribers for the following four notification types:

-   Terminate Session
-   End Shell
-   Logoff
-   Create Session

When the metric is expanded, these four notification types are presented as sub-metrics. Each of these types has a list of subscribers (for example, profiles and GPClient) as additional sub-metrics, and each subscriber lists the specific instances of **Connect to Subscriber** and **Call Subscriber** for that subscriber.

In any scenario, Winlogon subscribers can delay shutdown/suspend by taking too long to process these notifications. For example, a profile service (Profiles) must synchronize the user profile if the **Roaming (Remote) Profiles** feature is enabled on the computer. As another example, a Group Policy client (GPClient) might be configured by a system or domain policy to perform certain tasks at user logoff. These tasks are typically configured by a system or domain administrator.

**Typical Influencing Factors**

When you examine this metric, you should focus on the Winlogon Subscribers.

**Analysis and Remediation Steps**

Examine times of individual subscriber operations. Specific issues are usually generated for subscribers that have longer durations. Open WPA to the time interval of a subscriber for more insight. For example, if a GPClient subscriber call takes 10 seconds, an examination of that period in WPA can reveal that a certain custom script runs for 9 seconds out of 10. This points out that the script is a highly-probable root cause of the delay.

**Additional Information**

[MSDN: Winlogon Notification Events](http://go.microsoft.com/fwlink/?LinkId=247505)

