---
title: HeapEventCollectorId
description: HeapEventCollectorId
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: dcbc758e-bf3e-472b-8d7a-cfd8d357f193
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# HeapEventCollectorId

Represents an identifier for a collector of heap events for the profile.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<**HeapEventCollectorId**\>


## Syntax

```
<HeapEventCollectorId Value = IdType>

  <!-- Child elements -->
  BufferSize,
  Buffers,
  StackCaching,
  HeapEventProviders

</HeapEventCollectorId>
```


## Attributes and Elements


### Attributes

| Attribute | Description                                   | Data type                                                                             | Required | Default |
| :-------- | :-------------------------------------------- | :------------------------------------------------------------------------------------ | :------- | :------ |
| **Value** | Uniquely identifies the heap event collector. | String that must have at least one character and cannot contain colons (:) or spaces. | Yes      |         |


### Child Elements

| Element                                     | Description                                                                                                                                                                                                            | Requirement          |
| :------------------------------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------- |
| [BufferSize](buffersize.md)                 | Describes the size of each buffer, in KB.                                                                                                                                                                              | Required, exactly 1. |
| [Buffers](buffers.md)                       | Describes either the number of buffers to be allocated when starting a session or the percentage of total memory to be allocated for the session, depending on the value of the **PercentageOfTotalMemory** attribute. | Required, exactly 1. |
| [StackCaching](stackcaching.md)             | Describes stack caching attributes of collectors.                                                                                                                                                                      |                      |
| [HeapEventProviders](heapeventproviders.md) | Represents a collection of heap event provider identifiers and heap event providers.                                                                                                                                   | Required, exactly 1. |


### Parent Elements

| Element                   | Description                                                   |
| :------------------------ | :------------------------------------------------------------ |
| [Profile](profile-wpr.md) | Represents a collection of problem categories and collectors. |


## Related topics

[Elements](elements.md)

