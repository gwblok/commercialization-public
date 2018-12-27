---
title: WakeupDelay
description: WakeupDelay
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d93d6b02-b07b-4732-9f69-61685748ea6b
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# WakeupDelay

Indicates the delay, in seconds, when emerging from a sleep state for an [OnOffTransitionConfiguration](onofftransitionconfiguration.md) element.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[OnOffTransitionConfigurations](onofftransitionconfigurations.md)\>
    * \<[OnOffTransitionConfiguration](onofftransitionconfiguration.md)\>
      * \<**WakeupDelay**\>


## Syntax

```
<WakeupDelay Value = SimpleDelayValueType>
</WakeupDelay>
```


## Attributes and Elements


### Attributes

| Attribute | Description                                                                                   | Data Type | Required | Default |
| :-------- | :-------------------------------------------------------------------------------------------- | :-------- | :------- | :------ |
| **Value** | Describes the length of the delay, in seconds. Possible values are 1 through 3600, inclusive. | Integer   | Yes      |         |


### Child Elements

None.


### Parent Elements

| Element                                                         | Description                                    |
| :-------------------------------------------------------------- | :--------------------------------------------- |
| [OnOffTransitionConfiguration](onofftransitionconfiguration.md) | Represents an on/off transition configuration. |


## Example

The following code example shows the configuration of this element.

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

