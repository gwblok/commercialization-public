---
title: TransitionTag
description: TransitionTag
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ead6001f-02f3-4a85-a207-7af8e558a8f2
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# TransitionTag

Represents the transition tag for an [OnOffTransitionConfiguration](onofftransitionconfiguration.md) element.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[OnOffTransitionConfigurations](onofftransitionconfigurations.md)\>
    * \<[OnOffTransitionConfiguration](onofftransitionconfiguration.md)\>
      * \<**TransitionTag**\>


## Syntax

```
<TransitionTag Value = TransitionTagType>
</TransitionTag>
```


## Attributes and Elements


### Attributes

| Attribute | Description                               | Data type                                                                                                                                                                                                                                                                                           | Required | Default |
| :-------- | :---------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Value** | String that is inserted in the file name. | String that does not contain any of the following characters: <ul> <li>Forward slash (/)</li> <li>Backslash (&#92;)</li> <li>Colon (:)</li> <li>Asterisk (*)</li> <li>Question mark (?)</li> <li>Pipe symbol (&#124;)</li> <li>Right angle bracket (&gt;)</li> <li>Double quote (&quot;)</li> </ul> | Yes      |         |


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

