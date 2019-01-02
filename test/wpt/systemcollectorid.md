---
title: SystemCollectorId
description: SystemCollectorId
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bbaa7eb7-a7be-4b1d-a72c-087c7bf2fbef
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# SystemCollectorId

Represents the identifier of a system collector.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<**SystemCollectorId**\>


## Syntax

```
<SystemCollectorId Value = IdType>

  <!-- Child elements -->
  BufferSize,
  Buffers,
  StackCaching,
  SystemProviderId,
  SystemProvider

</SystemCollectorId>
```


## Attributes and Elements


### Attributes

| Attribute | Description               | Data type                                                                             | Required | Default |
| :-------- | :------------------------ | :------------------------------------------------------------------------------------ | :------- | :------ |
| **Value** | Describes the identifier. | String that must have at least one character and cannot contain colons (:) or spaces. | Yes      |         |


### Child Elements

| Element                                 | Description                                                              | Requirement          |
| :-------------------------------------- | :----------------------------------------------------------------------- | :------------------- |
| [BufferSize](buffersize.md)             | Describes the size of each buffer, in KB.                                | Required, exactly 1. |
| [Buffers](buffers.md)                   | Describes the number of buffers to be allocated when starting a session. | Required, exactly 1. |
| [StackCaching](stackcaching.md)         | Describes stack caching attributes of collectors.                        |                      |
| [SystemProviderId](systemproviderid.md) | Represents a system provider identifier.                                 | Optional, 1 or more. |
| [SystemProvider](systemprovider.md)     | Represents a system provider.                                            | Optional, 1 or more. |


### Parent Elements

| Element                     | Description                                       |
| :-------------------------- | :------------------------------------------------ |
| [Collectors](collectors.md) | Represents a collection of collector identifiers. |


## Related topics

[Elements](elements.md)

