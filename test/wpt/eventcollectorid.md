---
title: EventCollectorId
description: EventCollectorId
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a5a87699-9bd5-4ae9-9707-773ece45b4fc
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# EventCollectorId

Represents an event collector identifier.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<**EventCollectorId**\>


## Syntax

```
<EventCollectorId Value = IdType>

  <!-- Child elements -->
  BufferSize,
  Buffers,
  StackCaching,
  EventProviders

</EventCollectorId>
```


## Attributes and Elements


### Attributes

| Attribute | Description                              | Data type                                                                             | Required | Default |
| :-------- | :--------------------------------------- | :------------------------------------------------------------------------------------ | :------- | :------ |
| **Value** | Uniquely identifies the event collector. | String that must have at least one character and cannot contain colons (:) or spaces. | Yes      |         |


### Child Elements

| Element                             | Description                                                                | Requirement          |
| :---------------------------------- | :------------------------------------------------------------------------- | :------------------- |
| [BufferSize](buffersize.md)         | Describes the size of each buffer, in KB.                                  | Required, exactly 1. |
| [Buffers](buffers.md)               | Describes the number of buffers to be allocated when starting a session.   | Required, exactly 1. |
| [StackCaching](stackcaching.md)     | Describes stack caching attributes of collectors.                          |                      |
| [EventProviders](eventproviders.md) | Represents a collection of event provider identifiers and event providers. | Required, exactly 1. |


### Parent Elements

| Element                     | Description                                                                                                                      |
| :-------------------------- | :------------------------------------------------------------------------------------------------------------------------------- |
| [Collectors](collectors.md) | Represents a collection of system collector identifiers, event collector identifiers, and optionally heap collector identifiers. |


## Related topics

[Elements](elements.md)

