---
title: HeapEventProviders
description: HeapEventProviders
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b4582698-fb7f-4158-b41c-d2f1c53f3f87
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# HeapEventProviders

Represents a collection of heap event provider identifiers and heap event providers.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[HeapEventCollectorId](heapeventcollectorid.md)\>
          * \<**HeapEventProviders**\>


## Syntax

```
<HeapEventProviders Operation = "Set" | "Add" | “Remove” >

  <!-- Child elements -->
  HeapEventProviderId,
  HeapEventProvider

</HeapEventProviders>
```


## Attributes and Elements


### Attributes

| Attribute     | Description                                         | Data type                                                                                             | Required | Default |
| :------------ | :-------------------------------------------------- | :---------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Operation** | Indicates whether providers should be set or added. | This attribute can have one of the following values: <ul><li>Set</li><li>Add</li><li>Remove</li></ul> | No       | Set     |


### Child Elements

| Element                                       | Description                                  | Requirement             |
| :-------------------------------------------- | :------------------------------------------- | :---------------------- |
| [HeapEventProviderId](heapeventproviderid.md) | Represents a heap event provider identifier. | Optional, zero or more. |
| [HeapEventProvider](heapeventprovider.md)     | Represents a heap event provider.            | Optional, zero or more. |


### Parent Elements

| Element                                         | Description                                   |
| :---------------------------------------------- | :-------------------------------------------- |
| [HeapEventCollectorId](heapeventcollectorid.md) | Represents a heap event collector identifier. |


## Related topics

[Elements](elements.md)

