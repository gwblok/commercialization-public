---
title: HeapEventProvider
description: HeapEventProvider
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0f2fe538-bfd6-490b-b1c8-8f151153b8ef
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# HeapEventProvider

Represents a provider of heap events for the profile.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<**HeapEventProvider**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[HeapEventCollectorId](heapeventcollectorid.md)\>
          * \<[HeapEventProviders](heapeventproviders.md)\>
            * \<**HeapEventProvider**\>


## Syntax

```
<HeapEventProvider Id   = IdType
                   Base = string>

  <!-- Child elements -->
  HeapProcessIds

</HeapEventProvider>
```


## Attributes and Elements


### Attributes

| Attribute | Description                                  | Data type                                                                             | Required | Default |
| :-------- | :------------------------------------------- | :------------------------------------------------------------------------------------ | :------- | :------ |
| **Id**    | Uniquely identifies the heap event provider. | String that must have at least one character and cannot contain colons (:) or spaces. | Yes      |         |
| **Base**  | Indicates the base heap event provider.      | string                                                                                | No       |         |


### Child Elements

| Element                             | Description                                          | Requirement          |
| :---------------------------------- | :--------------------------------------------------- | :------------------- |
| [HeapProcessIds](heapprocessids.md) | Represents a collection of heap process identifiers. | Required, exactly 1. |


### Parent Elements

| Element                                     | Description                                                                          |
| :------------------------------------------ | :----------------------------------------------------------------------------------- |
| [HeapEventProviders](heapeventproviders.md) | Represents a collection of heap event provider identifiers and heap event providers. |
| [Profiles](profiles.md)                     | Represents a collection of collectors, providers, and profiles.                      |


## Remarks

Derived heap event providers have all the attributes of the base provider by default. These can be overridden by explicitly specifying them in the derived provider. For more information, see [Inheritance](inheritance.md).


## Related topics

[Elements](elements.md)

