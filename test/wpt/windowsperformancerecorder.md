---
title: WindowsPerformanceRecorder
description: WindowsPerformanceRecorder
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e17ce0a4-9621-4611-a781-2750fba3b0cd
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# WindowsPerformanceRecorder

This element is the root element of the schema. It represents metadata about the authoring of profiles.


## Element Hierarchy

* \<**WindowsPerformanceRecorder**\>


## Syntax

```
<WindowsPerformanceRecorder Version   = float
                            Author    = string
                            Team      = string
                            Copyright = string
                            Company   = string
                            Comments  = string
                            Tag       = string>

  <!-- Child elements -->
  Profiles,
  TraceMergeProperties,
  OnOffTransitionConfigurations

</WindowsPerformanceRecorder>
```


## Attributes and Elements


### Attributes

| Attribute     | Description                                                                     | Data type | Required | Default |
| :------------ | :------------------------------------------------------------------------------ | :-------- | :------- | :------ |
| **Version**   | Indicates the version of the profile.                                           | float     | Yes      |         |
| **Author**    | Indicates the author of the profile.                                            | string    | Yes      |         |
| **Team**      | Indicates the team that created the profile.                                    | string    | No       |         |
| **Copyright** | Represents copyright information.                                               | string    | No       |         |
| **Company**   | Indicates the company that created the profile.                                 | string    | No       |         |
| **Comments**  | Represents optional descriptive comments for the profiles.                      | string    | No       |         |
| **Tag**       | Represents a tagged value that can be used to differentiate different profiles. | string    | No       |         |


### Child Elements

| Element                                                           | Description                                                     | Requirement          |
| :---------------------------------------------------------------- | :-------------------------------------------------------------- | :------------------- |
| [Profiles](profiles.md)                                           | Represents a collection of collectors, providers, and profiles. | Required, exactly 1. |
| [TraceMergeProperties](tracemergeproperties.md)                   | Represents a collection of trace merge properites.              | Optional, zero or 1. |
| [OnOffTransitionConfigurations](onofftransitionconfigurations.md) | Represents a collection of on/off transition configurations.    | Optional, zero or 1. |


### Parent Elements

None.


## Related topics

[Elements](elements.md)

