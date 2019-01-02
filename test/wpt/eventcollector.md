---
title: EventCollector
description: EventCollector
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d7c94d21-b834-44f2-bad0-f0af6555bb5d
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# EventCollector

Represents an event collector for the profile.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<**EventCollector**\>


## Syntax

```
<EventCollector Id             = IdType
                Base           = string
                Name           = string
                FileName       = string
                Realtime       = boolean
                Private        = boolean
                ProcessPrivate = boolean
                Secure         = boolean>

  <!-- Child elements -->
  BufferSize,
  Buffers,
  StackCaching

</EventCollector>
```


## Attributes and Elements


### Attributes

<table>
<thead align="left" valign="bottom">
<tr class="header">
<th>Attribute</th>
<th>Description</th>
<th>Data type</th>
<th>Required</th>
<th>Default</th>
</tr>
</thead>
<tbody align="left" valign="top">
<tr class="odd">
<td><strong>Id</strong></td>
<td>Uniquely identifies the event collector.</td>
<td>String that must have at least one character and cannot contain colons (:) or spaces.</td>
<td>Yes</td>
<td></td>
</tr>
<tr class="even">
<td><strong>Base</strong></td>
<td>Identifies the base of the event collector.</td>
<td>string</td>
<td>No</td>
<td></td>
</tr>
<tr class="odd">
<td><strong>Name</strong></td>
<td>Indicates the name of the ETW session.</td>
<td>string</td>
<td>Yes</td>
<td></td>
</tr>
<tr class="even">
<td><strong>FileName</strong></td>
<td>Indicates the file to which to log events.</td>
<td>string</td>
<td>Yes</td>
<td></td>
</tr>
<tr class="odd">
<td><strong>Realtime</strong></td>
<td>Indicates whether the event collector operates in real time.</td>
<td>boolean</td>
<td>No</td>
<td>false</td>
</tr>
<tr class="even">
<td><strong>Private</strong></td>
<td>If set to &quot;true&quot;, indicates a user-mode session that runs in the same process as its event provider. If set to &quot;false&quot;, indicates a global user-mode session.</td>
<td>boolean</td>
<td>No</td>
<td>false</td>
</tr>
<tr class="odd">
<td><strong>ProcessPrivate</strong></td>
<td>If set to &quot;true&quot;, indicates a user-mode session that runs in the same process as its event provider and should be controlled only by the process that registered the provider. If set to &quot;false&quot;, indicates a global user-mode session. Use this attribute in conjunction with the <strong>Private</strong> attribute.</td>
<td>boolean</td>
<td>No</td>
<td>false</td>
</tr>
<tr class="even">
<td><strong>Secure</strong></td>
<td>If set to &quot;true&quot;, indicates that only users with administrative privileges and proper access rights can control the session. If set to &quot;false&quot;, indicates that all users can control the session.</td>
<td>boolean</td>
<td>No</td>
<td>false</td>
</tr>
</tbody>
</table>


### Child Elements

| Element                         | Description                                                                                                                                                                                                     | Requirement          |
| :------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------- |
| [BufferSize](buffersize.md)     | Describes the size of each buffer, in KB.                                                                                                                                                                       | Required, exactly 1. |
| [Buffers](buffers.md)           | Describes the number of buffers to be allocated when starting a session or the percentage of total memory to be allocated for the session, depending on the value of the **PercentageOfTotalMemory** attribute. | Required, exactly 1. |
| [StackCaching](stackcaching.md) | Describes stack caching attributes of collectors.                                                                                                                                                               |                      |


### Parent Elements

| Element                 | Description                                                     |
| :---------------------- | :-------------------------------------------------------------- |
| [Profiles](profiles.md) | Represents a collection of collectors, providers, and profiles. |


## Remarks

System collector definitions must precede event collector definitions.

Derived collectors inherit all attributes of the base collector unless they are explicitly specified in the derived collector. For more information, see [Inheritance](inheritance.md).


## Example

The following code example defines an event collector with 64 buffers of 128 KB each.

```xml
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

