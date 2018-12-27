---
title: Winlogon Resume Duration
description: On/Off assessment results for the Winlogon resume transition phase 


ms.date: 11/17/2017
ms.topic: article


localizationpriority: medium
---

# Winlogon Resume Duration

**Most Applicable to:** Winlogon subscriber developers, group policy script owners, system administrators, credential provider writers

**Relevant Assessments:**

-   Boot Performance (Fast Startup)
-   Hibernate Performance

This metric represents a timespan of multiple Winlogon callouts and operations, such as interaction with Winlogon subscribers. This metric is not the accumulated time that is spent in subscriber notifications, and it should not be treated as such.

**Detailed Sub-metrics**

Boot Performance (Fast Startup) is the only assessment that provides additional sub-metrics for this metric. When the metric is expanded, a more detailed phase view is presented that includes the times incurred by each of the Winlogon subscribers. During resume, Winlogon issues synchronous subscriber notifications to registered subscribers for the following two notification types:

-   Logon
-   Start Shell

When it is expanded, these two notification types are presented as sub-metrics. Each of these types has a list of subscribers (for example, profiles or GPClient) as additional sub-metrics. Each subscriber lists the specific instances of **Connect to Subscriber** and **Call Subscriber** for that subscriber.

For all scenarios, Winlogon subscribers can delay shutdown by taking too long to process these notifications. For example, a profile service (Profiles) must synchronize the user profile if the **Roaming (Remote) Profiles** feature is enabled on that computer. Or, a group policy client (GPClient) might be configured by a system or domain policy to perform certain tasks upon user logon. These tasks are typically configured by a system or domain administrator, and generally run non-Microsoft owned scripts.

**Typical Influencing Factors**

When you examine this metric, you should focus on the Winlogon subscribers that process the notifications for Logon and Start Shell.

**Analysis and Remediation Steps**

Examine times of individual subscriber operations. Specific issues are usually generated for longer subscriber durations. You can also gain insight by opening WPA to the time interval of a subscriber. For example, if a GPClient subscriber call takes 10 seconds, an examination of that duration in WPA can reveal that a certain custom script is running for 9 seconds out of 10. This can be seen in the **Process Lifetimes** graph. It indicates that this script is a probable root cause for the delay.

**Additional Information**

[Winlogon Notification Events](http://go.microsoft.com/fwlink/?LinkId=247505)

