---
title: PoolTags
description: PoolTags
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 819088ce-bfda-4866-a97c-a85b768c5f7a
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# PoolTags

Represents a collection of a maximum of four pool tags. If the **Operation** attribute is specified, the **PoolTag** elements can be set or added to the collection.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[SystemProvider](systemprovider.md)\>
      * \<**PoolTags**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[SystemCollectorId](systemcollectorid.md)\>
          * \<[SystemProviderId](systemproviderid.md)\>
            * \<**PoolTags**\>
          * \<[SystemProvider](systemprovider.md)\>
            * \<**PoolTags**\>


## Syntax

```
<PoolTags Operation = "Set" | "Add" | “Remove” >

  <!-- Child elements -->
  PoolTag

</PoolTags>
```


## Attributes and Elements


### Attributes

| Attribute     | Description                                                    | Data type                                                                                                 | Required | Default |
| :------------ | :------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Operation** | Indicates whether **PoolTag** elements should be set or added. | This attribute can have one of the following values: <ul> <li>Set</li> <li>Add</li> <li>Remove</li> </ul> | No       | Set     |


### Child Elements

| Element               | Description                                                     |
| :-------------------- | :-------------------------------------------------------------- |
| [PoolTag](pooltag.md) | Describes the pool tags to be enabled for analyzing pool pages. |


### Parent Elements

| Element                                 | Description                              |
| :-------------------------------------- | :--------------------------------------- |
| [SystemProvider](systemprovider.md)     | Represents a system provider.            |
| [SystemProviderId](systemproviderid.md) | Represents a system provider identifier. |


## Related topics

[Elements](elements.md)

