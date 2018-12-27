---
title: Buffers
description: Buffers
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8f60d3e3-cb32-4879-8ac2-80ceaea945d3
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# Buffers

Describes either the number of buffers to be allocated when starting a session or the percentage of total memory to be allocated for the session, depending on the value of the **PercentageOfTotalMemory** attribute.


## Element Hierarchy

* &lt;[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[SystemCollector](systemcollector.md)\>
      * \<**Buffers**\>
    * \<[EventCollector](eventcollector.md)\>
      * \<**Buffers**\>
    * \<[HeapEventCollector](heapeventcollector.md)\>
        * \<**Buffers**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[SystemCollectorId](systemcollectorid.md)\>
          * \<**Buffers**\>
        * \<[EventCollectorId](eventcollectorid.md)\>
          * \<**Buffers**\>
        * \<[HeapEventCollectorId](heapeventcollectorid.md)\>
          * \<**Buffers**\>


## Syntax

```
<Buffers Operation               = "Set" | "Add" | “Remove”
         Value                   = unsignedLong
         PercentageOfTotalMemory = Boolean
         MaximumBufferSpace      = Boolean >
</Buffers>
```


## Attributes and Elements


### Attributes

| Attribute                   | Description                                                                                                                                                   | Data type                                                                                                 | Required | Default |
| :-------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------ | :-------------------------------------------------------------------------------------------------------- | :------- | :------ |
| **MaximumBufferSpace**      | Indicates the maximum size of the buffer, in megabytes, that will be used for collection. This value only applies when **PercentageOfTotalMemory** is `true`. | unsignedLong                                                                                              | No       |         |
| **Operation**               | Indicates whether buffers should be set or added.                                                                                                             | This attribute can have one of the following values: <ul> <li>Set</li> <li>Add</li> <li>Remove</li> </ul> | No       | Set     |
| **PercentageOfTotalMemory** | When set to `true`, limits the amount of memory that can be consumed to the value of **Value**.                                                               | Boolean                                                                                                   | No       | false   |
| **Value**                   | Indicates the number of buffers, or if **PercentageOfTotalMemory** is set to `true`, the percentage of memory for the buffers.                                | unsignedLong                                                                                              | Yes      |         |


### Child Elements

None.


### Parent Elements

| Element                                         | Description                                   |
|:------------------------------------------------|:----------------------------------------------|
| [EventCollector](eventcollector.md)             | Represents an event collector.                |
| [EventCollectorId](eventcollectorid.md)         | Represents an event collector identifier.     |
| [HeapEventCollector](heapeventcollector.md)     | Represents a heap event collector.            |
| [HeapEventCollectorId](heapeventcollectorid.md) | Represents a heap event collector identifier. |
| [SystemCollector](systemcollector.md)           | Represents a system collector.                |
| [SystemCollectorId](systemcollectorid.md)       | Represents a system collector identifier.     |


## Remarks

This element is used only for in-memory capture.


## Example

The following examples show how this element is used in system collector and event collector definitions.

The first example sets the buffer size to 512 KB and limits the total amount of memory consumed to 3 percent. The second example sets 64 buffers of 128 KB each.

```xml
<SystemCollector
  Id="WPRSystemCollector"
  Name="NT Kernel Logger"
  FileName="WPRKernel.etl">
  <BufferSize
    Value="512"/> 
  <Buffers
    Value="3"
    PercentageOfTotalMemory="true"/>
</SystemCollector>

<EventCollector
  Id="WPREventCollector"
  Name="WPR Event Collector"
  FileName="somefilename.etl">
  <BufferSize
    Value="128"/>
  <Buffers
    Value="64"/>
</EventCollector>
```


## Related topics

[Elements](elements.md)

[BufferSize](buffersize.md)

[SystemCollector](systemcollector.md)

[EventCollector](eventcollector.md)

[HeapEventCollector](heapeventcollector.md)

