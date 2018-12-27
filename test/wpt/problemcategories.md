---
title: ProblemCategories
description: ProblemCategories
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 02997314-797c-468c-b1d7-3650e6f969e3
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# ProblemCategories

Represents a collection of problem categories. This element is for internal use only.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[Profile](profile-wpr.md)\>
      * \<**ProblemCategories**\>


## Syntax

```
<ProblemCategories Operation = "Set" | "Add" | “Remove” >

  <!-- Child elements -->
  ProblemCategory

</ProblemCategories>
```


## Attributes and Elements

### Attributes

| Attribute     | Description                                                            | Data type                                                                                                 | Required | Default |
| :------------ | :--------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Operation** | Indicates whether **ProblemCategory** elements should be set or added. | This attribute can have one of the following values: <ul> <li>Set</li> <li>Add</li> <li>Remove</li> </ul> | No       | Set     |


### Child Elements

| Element                               | Description                    | Requirement          |
| :------------------------------------ | :----------------------------- | :------------------- |
| [ProblemCategory](problemcategory.md) | Represents a problem category. | Required, 1 or more. |


### Parent Elements

| Element                   | Description                                                   |
| :------------------------ | :------------------------------------------------------------ |
| [Profile](profile-wpr.md) | Represents a collection of problem categories and collectors. |


## Related topics

[Elements](elements.md)

