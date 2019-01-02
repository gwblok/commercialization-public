---
title: TraceMergeProperty
description: TraceMergeProperty
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b3640f46-7bf4-4ee3-8094-ace27f275bd8
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# TraceMergeProperty

Contains configurations that are applied when recordings from multiple profiles are merged. This element is for internal use only.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[TraceMergeProperties](tracemergeproperties.md)\>
    * \<**TraceMergeProperty**\>


## Syntax

```
<TraceMergeProperty Id   = IdType
                    Name = string
                    Base = string>

  <!-- Child elements -->
  DeletePreMergedTraceFiles,
  FileCompression
  CustomEvents
</TraceMergeProperty>
```


## Attributes and Elements


### Attributes

| Attribute | Description                                                                                                                                                                                  | Data type                                                                             | Required | Default |
| :-------  | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------ | :------- | :------ |
| **ID**    | Uniquely identifies this element.                                                                                                                                                            | String that must have at least one character and cannot contain colons (:) or spaces. | Yes      |         |
| **Name**  | Indicates the name of this element.                                                                                                                                                          | string                                                                                | Yes      |         |
| **Base**  | Indicates the base of this element. Derived elements have all the attributes of the base by default. You can override these attributes by explicitly specifying them in the derived element. | string                                                                                | No       |         |


### Child Elements

| Element                                                   | Description                                                        | Requirement | Possible Values |
| :-------------------------------------------------------- | :----------------------------------------------------------------- | :---------- | :-------------- |
| [DeletePreMergedTraceFiles](deletepremergedtracefiles.md) | Indicates whether to delete premerged event trace log (ETL) files. | Optional    | true, false     |
| [FileCompression](filecompression.md)                     | Indicates whether to compress the ETL file.                        | Optional    | true, false     |
| [CustomEvents](customevents.md)                           | Represents a collection of custom events.                          | Optional    | true, false     |


### Parent Elements

| Element                                         | Description                                        |
| :---------------------------------------------- | :------------------------------------------------- |
| [TraceMergeProperties](tracemergeproperties.md) | Represents a collection of trace merge properites. |


## Example

The following code example shows a trace merge property definition.

```xml
<TraceMergeProperty
  Id="TraceMerge_Default"
  Name="TraceMerge_Default">
  <DeletePreMergedTraceFiles
    Value="true"/>
  <FileCompression
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

