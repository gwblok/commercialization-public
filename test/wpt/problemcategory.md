---
title: ProblemCategory
description: ProblemCategory
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 93db9658-1b8a-4713-8cac-702034d017d3
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# ProblemCategory

Represents a problem category for the profile. This element is for internal use only.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[Profile](profile-wpr.md)\>
      * \<[ProblemCategories](problemcategories.md)\>
        * \<**ProblemCategory**\>


## Syntax

```
<ProblemCategory Value = "First Level Triage" | "CPU" | "Storage" ...>
</ProblemCategory>
```


## Attributes and Elements

### Attributes

| Attribute | Description                    | Data type                                                                                                                                                                                                                 | Required | Default |
| :-------- | :----------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :------- | :------ |
| **Value** | Describes the type of problem. | This attribute can have one of the following values: <ul> <li>First Level Triage</li> <li>CPU</li> <li>Storage</li> <li>Network</li> <li>Memory</li> <li>Multimedia</li> <li>Energy</li> <li>On/Off Transition</li> </ul> | Yes      |         |

### Child Elements

None.


### Parent Elements

| Element                                   | Description                                    |
| :---------------------------------------- | :--------------------------------------------- |
| [ProblemCategories](problemcategories.md) | Represents a collection of problem categories. |


## Related topics

[Elements](elements.md)

