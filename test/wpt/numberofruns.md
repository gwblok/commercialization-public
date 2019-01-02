---
title: NumberOfRuns
description: NumberOfRuns
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8468fba0-3470-4813-b388-83c94550c446
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# NumberOfRuns

Indicates the number of times that an on-off transition is run.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[OnOffTransitionConfigurations](onofftransitionconfigurations.md)\>
    * \<[OnOffTransitionConfiguration](onofftransitionconfiguration.md)\>
      * \<**NumberOfRuns**\>


## Syntax

```
<NumberOfRuns Value = SimpleValueType>
</NumberOfRuns>
```


## Attributes and Elements


### Attributes

| Attribute | Description                                   | Data type                                 | Required | Default |
| :-------- | :-------------------------------------------- | :---------------------------------------- | :------- | :------ |
| **Value** | Number of times the on/off transition is run. | Integer value equal to or greater than 1. | Yes      |         |


### Child Elements

None.


### Parent Elements

| Element                                                         | Description                                    |
| :-------------------------------------------------------------- | :--------------------------------------------- |
| [OnOffTransitionConfiguration](onofftransitionconfiguration.md) | Represents on on/off transition configuration. |


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

