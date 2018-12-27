---
title: TraceMergeProperties
description: TraceMergeProperties
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7771cdc2-3573-4a3b-a52b-70ef77f706dc
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# TraceMergeProperties

Represents a collection of [TraceMergeProperty](tracemergeproperty.md) element. This element is for internal use only.


## Element Syntax

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<**TraceMergeProperties**\>


## Syntax

```
<TraceMergeProperties>

  <!-- Child elements -->
  TraceMergeProperty

</TraceMergeProperties>
```


## Attributes and Elements


### Attributes

None.


### Child Elements

| Element                                     | Description                                                                                                  | Requirment           |
| :------------------------------------------ | :----------------------------------------------------------------------------------------------------------- | :------------------- |
| [TraceMergeProperty](tracemergeproperty.md) | Contains configurations that are applied when event trace log (ETL) files from multiple profiles are merged. | Required, 1 or more. |


### Parent Elements

| Element                                                     | Description                                             |
| :---------------------------------------------------------- | :------------------------------------------------------ |
| [WindowsPerformanceRecorder](windowsperformancerecorder.md) | Represents metadata about the authoring of the profile. |


## Example

The following code example shows how to define this element.

```xml
<TraceMergeProperties>
  <TraceMergeProperty
    Id="TraceMerge_Default"
    Name="TraceMerge_Default">
    <DeletePreMergedTraceFiles
      Value="true"/>
    <CustomEvents>
      <CustomEvent
        Value="ImageId"/>
      <CustomEvent
        Value="BuildInfo"/>
      <CustomEvent
        Value="VolumeMapping"/>
      <CustomEvent
        Value="EventMetadata"/>
      <CustomEvent
        Value="PerfTrackMetadata"/>
      <CustomEvent
        Value="WinSAT"/>
      <CustomEvent
        Value="NetworkInterface"/>
    </CustomEvents>
  </TraceMergeProperty>
</TraceMergeProperties>
```


## Related topics

[Elements](elements.md)

[Inheritance](inheritance.md)

