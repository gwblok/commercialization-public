---
title: HeapEventCollector
description: HeapEventCollector
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e8f6e4d9-b037-49ca-b816-cc7757b98b3d
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# HeapEventCollector

Represents a collector for heap events.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<**HeapEventCollector**\>


## Syntax

```
<HeapEventCollector Id       = IdType
                    Base     = string
                    Name     = string
                    FileName = string
                    Realtime = boolean
                    Secure   = boolean>

  <!-- Child elements -->
  BufferSize,
  Buffers,
  StackCaching

</HeapEventCollector>
```


## Attributes and Elements


### Attributes

| Attribute    | Description                                                                                                                                                                                       | Data type                                                                             | Required | Default |
| :----------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------ | :------- | :------ |
| **Id**       | Uniquely identifies the heap event collector.                                                                                                                                                     | String that must have at least one character and cannot contain colons (:) or spaces. | Yes      |         |
| **Base**     | Indicates the base of the collector.                                                                                                                                                              | string                                                                                | No       |         |
| **Name**     | Indicates the name of the heap event collector.                                                                                                                                                   | string                                                                                | Yes      |         |
| **FileName** | Indicates the name of the file to which events should be written.                                                                                                                                 | string                                                                                | Yes      |         |
| **Realtime** | Indicates whether the event collector operates in real time.                                                                                                                                      | boolean                                                                               | No       | false   |
| **Secure**   | If set to `true`, indicates that only users with administrative privileges and proper access rights can control the session. If set to `false`, indicates that all users can control the session. | boolean                                                                               | No       | true    |


### Child Elements

| Element                         | Description                                                                                                                                                                                                            | Requirement          |
| :------------------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------- |
| [BufferSize](buffersize.md)     | Describes the size of each buffer, in KB.                                                                                                                                                                              | Required, exactly 1. |
| [Buffers](buffers.md)           | Describes either the number of buffers to be allocated when starting a session or the percentage of total memory to be allocated for the session, depending on the value of the **PercentageOfTotalMemory** attribute. | Required, exactly 1. |
| [StackCaching](stackcaching.md) | Describes stack caching attributes of collectors.                                                                                                                                                                      |                      |


### Parent Elements

| Element                 | Description                                                     |
| :---------------------- | :-------------------------------------------------------------- |
| [Profiles](profiles.md) | Represents a collection of collectors, providers, and profiles. |


## Remarks

Derived event collectors have the attributes of the base collector by default. These can be overridden by explicitly specifying them in the derived collector. For more information, see [Inheritance](inheritance.md).


## Related topics

[Elements](elements.md)

[Inheritance](inheritance.md)

