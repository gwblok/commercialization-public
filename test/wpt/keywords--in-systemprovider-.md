---
title: Keywords (in SystemProvider)
description: Keywords (in SystemProvider)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bf98056c-7863-4430-9522-ac2f74048481
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# Keywords (in SystemProvider)

Represents a collection of keywords. If the **Operation** attribute is specified, the **Keyword** elements can be set or added to the collection.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[SystemProvider](systemprovider.md)\>
      * \<**Keywords (in SystemProvider)**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[SystemCollectorId](systemcollectorid.md)\>
          * \<[SystemProviderId](systemproviderid.md)\>
            * \<**Keywords (in SystemProvider)**\>
          * \<[SystemProvider](systemprovider.md)\>
            * \<**Keywords (in SystemProvider)**\>


## Syntax

```
<Keywords Operation = OperationEnumeration = "Set" | "Add" | “Remove” >

  <!-- Child elements -->
  Keyword,
  CustomKeyword

</Keywords>
```


## Attributes and Elements


### Attributes

| Attribute     | Description                                        | Data type                                                                                                 | Required | Default |
| :------------ | :------------------------------------------------- | :-------------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Operation** | Indicates whether keywords should be set or added. | This attribute can have one of the following values: <ul> <li>Set</li> <li>Add</li> <li>Remove</li> </ul> | No       | Set     |


### Child Elements

| Element                                                       | Description                                                                 | Requirement             |
| :------------------------------------------------------------ | :-------------------------------------------------------------------------- | :---------------------- |
| [Keyword (in SystemProvider)](keyword--in-systemprovider-.md) | Describes the kernel flags that can be enabled for the kernel-mode session. | Required, 1 or more.    |
| [CustomKeyword](customkeyword.md)                             | Describes a custom keyword.                                                 | Optional, zero or more. |


### Parent Elements

| Element                                 | Description                              |
| :-------------------------------------- | :--------------------------------------- |
| [SystemProvider](systemprovider.md)     | Represents a system provider.            |
| [SystemProviderId](systemproviderid.md) | Represents a system provider identifier. |


## Related topics

[Elements](elements.md)

