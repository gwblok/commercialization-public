---
title: PoolTag
description: PoolTag
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e544351c-bb0a-4450-a6d4-5fc230bf684d
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# PoolTag

Describes the pool tags to be enabled for analyzing pool pages.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[SystemProvider](systemprovider.md)\>
      * \<[PoolTags](pooltags.md)\>
        * \<**PoolTag**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[SystemCollectorId](systemcollectorid.md)\>
          * \<[SystemProviderId](systemproviderid.md)\>
            * \<[PoolTags](pooltags.md)\>
              * \<**PoolTag**\>
          * \<[SystemProvider](systemprovider.md)\>
            * \<[PoolTags](pooltags.md)\>
              * \<**PoolTag**\>


## Syntax

```
<PoolTag Value = SystemPoolTagAttributeType>
</PoolTag>
```


## Attributes and Elements


### Attributes

| Attribute | Description                          | Data type                                             | Required | Default |
| :-------- | :----------------------------------- | :---------------------------------------------------- | :------- | :------ |
| **Value** | Describes the value of this element. | String that must be one to four characters in length. | Yes      |         |


### Child Elements

None.


### Parent Elements

| Element                 | Description                           |
| :---------------------- | :------------------------------------ |
| [PoolTags](pooltags.md) | Represents a collection of pool tags. |


## Related topics

[Elements](elements.md)

