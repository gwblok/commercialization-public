---
title: CustomEvent
description: CustomEvent
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4ce7091b-4e6a-40c3-aeff-1c9434310f44
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# CustomEvent

Represents a custom event.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[TraceMergeProperties](tracemergeproperties.md)\>
    * \<[TraceMergeProperty](tracemergeproperty.md)\>
      * \<[CustomEvents](customevents.md)\>
        * \<**CustomEvent**\>


## Syntax

```
<CustomEvent Value = "None" | "ImageId" | "BuildInfo" | ...>
</CustomEvent>
```


## Attributes and Elements


### Attributes

| Attribute | Description                              | Data type                                                                                                                                                                                                                            | Required | Default |
| :-------- | :--------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Value** | Describes the value of the custom event. | This attribute can have one of the following values: <ul> <li>None</li> <li>ImageId</li> <li>BuildInfo</li> <li>VolumeMapping</li> <li>EventMetadata</li> <li>PerfTrackMetadata</li> <li>WinSAT</li> <li>NetworkInterface</li> </ul> | Yes      |         |


### Child Elements

None.


### Parent Elements

| Element                         | Description                               |
|:--------------------------------|:------------------------------------------|
| [CustomEvents](customevents.md) | Represents a collection of custom events. |


## Example

The following code example shows how this element is used in a trace merge property definition.

```xml
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
```


## Related topics

[Elements](elements.md)

