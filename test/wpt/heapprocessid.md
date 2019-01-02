---
title: HeapProcessId
description: HeapProcessId
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b0d95f7c-af59-4452-9a60-3ab1e06b072a
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# HeapProcessId

Uniquely identifies a heap process.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[HeapEventProvider](heapeventprovider.md)\>
    * \<[HeapProcessIds](heapprocessids.md)\>
      * \<**HeapProcessId**\>
  * \<[Profiles](profiles.md)\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[HeapEventCollectorId](heapeventcollectorid.md)\>
          * \<[HeapEventProviders](heapeventproviders.md)\>
            * \<[HeapEventProviderId](heapeventproviderid.md)\>
              * \<[HeapProcessIds](heapprocessids.md)\>
                * \<**HeapProcessId**\>
            * \<[HeapEventProvider](heapeventprovider.md)\>
              * \<[HeapProcessIds](heapprocessids.md)\>
                * \<**HeapProcessId**\>


## Syntax

```
<HeapProcessId Value = unsignedLong>
</HeapProcessId>
```


## Attributes and Elements


### Attributes

| Attribute | Description                 | Data type    | Required | Default |
| :-------- | :-------------------------- | :----------- | :------- | :------ |
| **Value** | Number of the heap process. | unsignedLong | Yes      |         |


### Child Elements

None.


### Parent Elements

| Element                             | Description                                          |
| :---------------------------------- | :--------------------------------------------------- |
| [HeapProcessIds](heapprocessids.md) | Represents a collection of heap process identifiers. |


## Related topics

[Elements](elements.md)

