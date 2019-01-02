---
title: OnOffTransitionConfigurations
description: OnOffTransitionConfigurations
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7046c6c0-8e74-47a1-a4ce-47a7dc5a43c0
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# OnOffTransitionConfigurations

Represents a collection of on/off transitions.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<**OnOffTransitionConfigurations**\>


## Syntax

```
<OnOffTransitionConfigurations>

  <!-- Child elements -->
  OnOffTransitionConfiguration

</OnOffTransitionConfigurations>
```


## Attributes and Elements


### Attributes

None.


### Child Elements

| Element                                                         | Description                                    | Requirement          |
| :-------------------------------------------------------------- | :--------------------------------------------- | :------------------- |
| [OnOffTransitionConfiguration](onofftransitionconfiguration.md) | Represents an on/off transition configuration. | Required, exactly 1. |


### Parent Elements

| Element                                                     | Description                                             |
| :---------------------------------------------------------- | :------------------------------------------------------ |
| [WindowsPerformanceRecorder](windowsperformancerecorder.md) | Represents metadata about the authoring of the profile. |


## Related topics

[Elements](elements.md)

