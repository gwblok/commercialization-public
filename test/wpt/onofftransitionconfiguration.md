---
title: OnOffTransitionConfiguration
description: OnOffTransitionConfiguration
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c9b194b8-c179-49da-ac8d-aae373c9d706
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# OnOffTransitionConfiguration

Represents an on/off transition configuration.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[OnOffTransitionConfigurations](onofftransitionconfigurations.md)\>
    * \<**OnOffTransitionConfiguration**\>


## Syntax

```
<OnOffTransitionConfiguration Id = IdType
                              Name = string
                              Type = "On/Off - Boot" | "On/Off - HybridBoot" | "On/Off - Shutdown" | ...>

  <!-- Child elements -->
  PrepareSystem,
  NumberOfRuns,
  PostBootDelay,
  WakeupDelay,
  TransitionTag

</OnOffTransitionConfiguration>
```


## Attributes and Elements

### Attributes

| Attribute | Description                                              | Data type                                                                                                                                                                                                                                        | Required | Default |
| :-------- | :------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Id**    | Uniquely identifies the on/off transition configuration. | String that must have at least one character and cannot contain colons (:) or spaces.                                                                                                                                                            | Yes      |         |
| **Name**  | Indicates the name of the configuration.                 | string                                                                                                                                                                                                                                           | Yes      |         |
| **Type**  | Indicates the type of on/off transition.                 | This attribute can have one of the following values: <ul> <li>On/Off - Boot</li> <li>On/Off - HybridBoot</li> <li>On/Off - Shutdown</li> <li>On/Off - RebootCycle</li> <li>On/Off - Standby/Resume</li> <li>On/Off - Hibernate/Resume</li> </ul> | Yes      |         |


### Child Elements

| Element                           | Description                                                       | Requirement          |
| :-------------------------------- | :---------------------------------------------------------------- | :------------------- |
| [PrepareSystem](preparesystem.md) | Indicates whether to prepare the system for an on/off transition. | Required, exactly 1. |
| [NumberOfRuns](numberofruns.md)   | Indicates the number of runs in the on/off transition.            | Required, exactly 1. |
| [PostBootDelay](postbootdelay.md) | Indicates the delay after booting.                                | Optional, zero or 1. |
| [WakeupDelay](wakeupdelay.md)     | Indicates the delay when emerging from a sleep state.             | Optional, zero or 1. |
| [TransitionTag](transitiontag.md) | Indicates the transition tag.                                     | Optional, zero or 1. |


### Parent Elements

| Element                                                           | Description                                   |
| :---------------------------------------------------------------- | :-------------------------------------------- |
| [OnOffTransitionConfigurations](onofftransitionconfigurations.md) | Represents a collection of on/off transition. |


## Example

The following code example shows how to configure this element.

```xml
<OnOffTransitionConfiguration
  Id="OnOffTransitionConfiguration_Default_Boot"
  Name="OnOffTransitionConfiguration_Default_Boot"
  Type="On/Off - Boot">
  <PrepareSystem Value="true"/>
  <NumberOfRuns Value="3"/>
  <PostBootDelay Value="120"/>
  <WakeupDelay Value="60"/>
  <TransitionTag Value="Boot"/>
</OnOffTransitionConfiguration>
```


## Related topics

[Elements](elements.md)

