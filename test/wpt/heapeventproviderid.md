---
title: HeapEventProviderId
description: HeapEventProviderId
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4f4da898-5dba-48f4-a203-d0acbcde6153
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# HeapEventProviderId

Represents an identifier for a provider of heap events.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[HeapEventCollectorId](heapeventcollectorid.md)\>
          * \<[HeapEventProviders](heapeventproviders.md)\>
            * \<**HeapEventProviderId**\>


## Syntax

```
<HeapEventProviderId Value = IdType>

  <!-- Child elements -->
  HeapProcessIds

</HeapEventProviderId>
```


## Attributes and Elements


### Attributes

| Attribute | Description                                  | Data type                                                                             | Required | Default |
| :-------- | :------------------------------------------- | :------------------------------------------------------------------------------------ | :------- | :------ |
| **Value** | Uniquely identifies the heap event provider. | String that must have at least one character and cannot contain colons (:) or spaces. | Yes      |         |


### Child Elements

| Element                             | Description                                          | Requirement          |
| :---------------------------------- | :--------------------------------------------------- | :------------------- |
| [HeapProcessIds](heapprocessids.md) | Represents a collection of heap process identifiers. | Required, exactly 1. |


### Parent Elements

| Element                                     | Description                                                                          |
| :------------------------------------------ | :----------------------------------------------------------------------------------- |
| [HeapEventProviders](heapeventproviders.md) | Represents a collection of heap event provider identifiers and heap event providers. |


## Related topics

[Elements](elements.md)

