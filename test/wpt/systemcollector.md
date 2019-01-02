---
title: SystemCollector
description: SystemCollector
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e7b9b910-9fe4-4dca-a61a-2599f67caf00
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# SystemCollector

Describes the configurations to enable the Event Tracing for Windows (ETW) kernel-mode session.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<**SystemCollector**\>


## Syntax

```
<SystemCollector Id       = IdType
                 Base     = string
                 Name     = "NT Kernel Logger" | "Circular Kernel Context Logger"
                 Realtime = boolean>

  <!-- Child elements -->
  BufferSize,
  Buffers,
  StackCaching

</SystemCollector>
```


## Attributes and Elements


### Attributes

| Attribute    | Description                                                                                                                                                                                    | Data type                                                                                                                         | Required | Default |
| :----------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Id**       | Uniquely identifies the system collector.                                                                                                                                                      | String that must have at least one character and cannot contain colons (:) or spaces.                                             | Yes      |         |
| **Base**     | Identifies the base of the system collector. Derived collectors have all the attributes of the base collector. These can be overridden by explicitly specifying them in the derived collector. | string                                                                                                                            | No       |         |
| **Name**     | Indicates the name of the system collector.                                                                                                                                                    | This attribute can have one of the following values: <ul> <li>NT Kernel Logger</li> <li>Circular Kernel Context Logger</li> </ul> | Yes      |         |
| **Realtime** | Indicates whether the collector works in real time.                                                                                                                                            | boolean                                                                                                                           | No       | false   |


### Child Elements

| Element                         | Description                                                              | Requirement          |
| :------------------------------ | :----------------------------------------------------------------------- | :------------------- |
| [BufferSize](buffersize.md)     | Describes the size of each buffer, in KB.                                | Required, exactly 1. |
| [Buffers](buffers.md)           | Describes the number of buffers to be allocated when starting a session. | Required, exactly 1. |
| [StackCaching](stackcaching.md) | Describes stack caching attributes of collectors.                        |                      |


### Parent Elements

| Element                 | Description                                                     |
| :---------------------- | :-------------------------------------------------------------- |
| [Profiles](profiles.md) | Represents a collection of collectors, providers, and profiles. |


## Remarks

System collector definitions should precede event collector definitions.


## Example

The following code example defines a system collector.

```xml
<SystemCollector
  Id="WPRSystemCollector”
  Name="NT Kernel Logger"
  FileName="WPRKernel.etl">
  <BufferSize Value="512"/>
  <Buffers Value="3" PercentageOfTotalMemory="true"/>
</SystemCollector>
```


## Related topics

[Elements](elements.md)

