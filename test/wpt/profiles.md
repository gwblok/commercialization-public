---
title: Profiles
description: Profiles
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 00b0d6dc-d14a-4c70-ab7b-4aa2250c2395
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# Profiles

Represents a collection of collectors, providers, and profiles.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<**Profiles**\>


## Syntax

```
<Profiles>

  <!-- Child elements -->
  SystemCollector,
  EventCollector,
  HeapEventCollector,
  SystemProvider,
  EventProvider,
  HeapEventProvider,
  Profile

</Profiles>
```


## Attributes and Elements


### Attributes

None.


### Child Elements

| Element                                     | Description                                                   | Requirement             |
| :------------------------------------------ | :------------------------------------------------------------ | :---------------------- |
| [SystemCollector](systemcollector.md)       | Represents a system collector.                                | Optional, zero or more. |
| [EventCollector](eventcollector.md)         | Represents an event collector.                                | Optional, zero or more. |
| [HeapEventCollector](heapeventcollector.md) | Represents a heap event collector.                            | Optional, zero or more. |
| [SystemProvider](systemprovider.md)         | Represents a system provider.                                 | Optional, zero or more. |
| [EventProvider](eventprovider.md)           | Represents an event provider.                                 | Optional, zero or more. |
| [HeapEventProvider](heapeventprovider.md)   | Represents a heap event provider.                             | Optional, zero or more. |
| [Profile](profile-wpr.md)                   | Represents a collection of problem categories and collectors. | Required, 1 to 4.       |


### Parent Elements

| Element                                                     | Description                                             |
| :---------------------------------------------------------- | :------------------------------------------------------ |
| [WindowsPerformanceRecorder](windowsperformancerecorder.md) | Represents metadata about the authoring of the profile. |


## Remarks

Only a single **Profiles** element can be defined in a **WindowsPerformanceRecorder** element.


## Related topics

[Elements](elements.md)

