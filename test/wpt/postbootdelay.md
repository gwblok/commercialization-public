---
title: PostBootDelay
description: PostBootDelay
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: fef41639-e619-456f-95a6-776aa0b0036a
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# PostBootDelay

Indicates the length of the delay, in seconds, after booting for an [OnOffTransitionConfiguration](onofftransitionconfiguration.md) element.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[OnOffTransitionConfigurations](onofftransitionconfigurations.md)\>
    * \<[OnOffTransitionConfiguration](onofftransitionconfiguration.md)\>
      * \<**PostBootDelay**\>


## Syntax

```
<PostBootDelay Value = SimpleDelayValueType>
</PostBootDelay>
```


## Attributes and Elements


### Attributes

| Attribute | Description                                    | Data type                                 | Required | Default |
| :-------- | :--------------------------------------------- | :---------------------------------------- | :------- | :------ |
| **Value** | Describes the length of the delay, in seconds. | Integer in the range from 1 through 3600. | Yes      |         |


### Child Elements

None.


### Parent Elements

| Element                                                         | Description                                    |
| :-------------------------------------------------------------- | :--------------------------------------------- |
| [OnOffTransitionConfiguration](onofftransitionconfiguration.md) | Represents an on/off transition configuration. |


## Example

The following example shows how to configure this element.

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

[WakeupDelay](wakeupdelay.md)

