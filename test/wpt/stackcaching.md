---
title: StackCaching
description: StackCaching
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 99afd74f-9423-4ff5-8dc7-24c1dd622b7d
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# StackCaching

Describes stack caching attributes of collectors.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[SystemCollector](systemcollector.md)\>
      * \<**StackCaching**\>
    * \<[EventCollector](eventcollector.md)\>
      * \<**StackCaching**\>
    * \<[HeapEventCollector](heapeventcollector.md)\>
      * \<**StackCaching**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[SystemCollectorId](systemcollectorid.md)\>
          * \<**StackCaching**\>
        * \<[EventCollectorId](eventcollectorid.md)\>
          * \<**StackCaching**\>
        * \<[HeapEventCollectorId](heapeventcollectorid.md)\>
          * \<**StackCaching**\>


## Syntax


## Attributes and Elements


### Attributes

| Attribute       | Description                              | Data type      | Required | Default |
| :-------------- | :--------------------------------------- | :------------- | :------- | :------ |
| **BucketCount** | Represents the number of buckets.        | Unsigned long. | Yes      |         |
| **CacheSize**   | Represents the size of the cache, in KB. | Unsigned long. | Yes      |         |


### Child Elements

None.


### Parent Elements

| Element                                         | Description                                                                                     |
| :---------------------------------------------- | :---------------------------------------------------------------------------------------------- |
| [EventCollector](eventcollector.md)             | Represents an event collector for the profile.                                                  |
| [EventCollectorId](eventcollectorid.md)         | Represents an event collector identifier.                                                       |
| [HeapEventCollector](heapeventcollector.md)     | Represents a collector for heap events.                                                         |
| [HeapEventCollectorId](heapeventcollectorid.md) | Represents an identifier for a collector of heap events for the profile.                        |
| [SystemCollector](systemcollector.md)           | Describes the configurations to enable the Event Tracing for Windows (ETW) kernel-mode session. |
| [SystemCollectorId](systemcollectorid.md)       | Represents the identifier of a system collector.                                                |


## Remarks

If you do not specify values for its attributes, this element is ignored.


## Related topics

[SystemCollector](systemcollector.md)

