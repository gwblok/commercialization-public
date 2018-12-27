---
title: PrepareSystem
description: PrepareSystem
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7ec136bc-f59a-4b36-9ae5-1e25c6fe06c4
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# PrepareSystem

Indicates whether to prepare the system for an [OnOffTransitionConfiguration](onofftransitionconfiguration.md) element.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[OnOffTransitionConfigurations](onofftransitionconfigurations.md)\>
    * \<[OnOffTransitionConfiguration](onofftransitionconfiguration.md)\>
      * \<**PrepareSystem**\>


## Syntax

```
<PrepareSystem Value = boolean>
</PrepareSystem>
```


## Attributes and Elements


### Attributes

| Attribute | Description                              | Data type | Required | Default |
| :-------- | :--------------------------------------- | :-------- | :------- | :------ |
| **Value** | Indicates whether to prepare the system. | boolean   | Yes      |         |


### Child Elements

None.


### Parent Elements

| Element                                                         | Description                                    |
| :-------------------------------------------------------------- | :--------------------------------------------- |
| [OnOffTransitionConfiguration](onofftransitionconfiguration.md) | Represents an on/off transition configuration. |


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

