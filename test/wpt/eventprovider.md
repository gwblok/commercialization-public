---
title: EventProvider
description: EventProvider
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bf7e4e86-e837-41f8-847f-42fc12c5a98c
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# EventProvider

Configures the Event Tracing for Windows (ETW) user-mode provider.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<**EventProvider**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[EventCollectorId](eventcollectorid.md)\>
          * \<[EventProviders](eventproviders.md)\>
            * \<**EventProvider**\>


## Syntax

```
<EventProvider Id               = IdType
               Name             = string
               Base             = string
               NonPageMemory    = boolean
               Stack            = boolean
               SID              = boolean
               TSID             = boolean
               Level            = unsigendByte
               CaptureStateOnly = boolean>

  <!-- Child elements -->
  Keywords,
  CaptureStateOnStart,
  CaptureStateOnSave

</EventProvider>
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
<td>Uniquely identifies the event provider.</td>
<td>String that must have at least one character and cannot contain colons (:) or spaces.</td>
<td>Yes</td>
<td></td>
</tr>
<tr class="even">
<td><strong>Name</strong></td>
<td>Indicates the name of the event provider.</td>
<td>This attribute can have one of the following values:
<ul>
<li><p>A registered Crimson provider, for example, &quot;Microsoft-Windows-Search-Core&quot;.</p></li>
<li><p>A provider GUID, for example &quot;49c2c27c-fe2d-40bf-8c4e-c3fb518037e7&quot;.</p></li>
<li><p>The name of a legacy provider, for example &quot;IE6&quot;.</p></li>
<li><p>A special-case name, such as &quot;PerfTrack&quot; or &quot;DotNetProvider&quot;.</p></li>
</ul></td>
<td>Yes</td>
<td></td>
</tr>
<tr class="odd">
<td><strong>ProcessExeFilter</strong></td>
<td>Filters an event based on the process .exe name specified.</td>
<td>This is an optional attribute you add to the <strong>EventProvider ID</strong> in the WPR profile. For example:
<ul>
<li><p>&quot;ProcessExeFilter=&quot;wpa.exe&quot;</p></li>
</ul>
<div class="alert">
<strong>Note</strong><br/><p>WPR essentially passes on the .exe name into the <a href="https://msdn.microsoft.com/library/windows/desktop/aa363758.aspx">EVENT_FILTER_DESCRIPTOR</a> structure.</p>
</div>
<div>

</div></td>
<td>No</td>
<td></td>
</tr>
<tr class="even">
<td><strong>Base</strong></td>
<td>Indicates the base for the provider.</td>
<td>string</td>
<td>No</td>
<td></td>
</tr>
<tr class="odd">
<td><strong>NonPagedMemory</strong></td>
<td>Indicates whether non-paged memory is to be used.</td>
<td>boolean</td>
<td>No</td>
<td>false</td>
</tr>
<tr class="even">
<td><strong>Stack</strong></td>
<td>Indicates whether the provider should capture stacks.</td>
<td>boolean</td>
<td>No</td>
<td>false</td>
</tr>
<tr class="odd">
<td><strong>SID</strong></td>
<td>Indicates whether to include the security identifier (SID) of the user to the extended data of logged events.</td>
<td>boolean</td>
<td>No</td>
<td>false</td>
</tr>
<tr class="even">
<td><strong>TSID</strong></td>
<td>Indicates whether the terminal session identifier is included in the extended data of logged events.</td>
<td>boolean</td>
<td>No</td>
<td>false</td>
</tr>
<tr class="odd">
<td><strong>Level</strong></td>
<td>Indicates the level value.</td>
<td>unsignedByte</td>
<td>No</td>
<td>Zero, which ETW treats as 0xFFFFFFFFFFFFFFFF.</td>
</tr>
<tr class="even">
<td><strong>CaptureStateOnly</strong></td>
<td>Indicates whether a provider is enabled only at start or save of a tracing session.</td>
<td>boolean</td>
<td>No</td>
<td>false</td>
</tr>
</tbody>
</table>


### Child Elements

| Element                                                       | Description                                                                                                                                        | Requirement          |
| :------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------- |
| [Keywords (in EventProvider)](keywords--in-eventprovider-.md) | Represents a collection of [Keyword (in EventProvider)](keyword--in-eventprovider-.md) elements.                                                   | Required, 1 or more. |
| [CaptureStateOnStart](capturestateonstart.md)                 | Represents a collection of [Keyword (in EventProvider)](keyword--in-eventprovider-.md) elements for events to be captured at the start of a trace. | Optional, zero or 1. |
| [CaptureStateOnSave](capturestateonsave.md)                   | Represents a collection of [Keyword (in EventProvider)](keyword--in-eventprovider-.md) elements for events to be captured when a trace is saved.   | Optional, zero or 1. |


### Parent Elements

| Element                             | Description                                                     |
| :---------------------------------- | :-------------------------------------------------------------- |
| [EventProviders](eventproviders.md) | Represents a collection of **EventProvider** elements.          |
| [Profiles](profiles.md)             | Represents a collection of collectors, providers, and profiles. |


## Remarks


Provider definition order is important. Definitions must appear in the following order in the .wprp file:

1.  Collectors
2.  System provider
3.  Event provider(s)

Optional inner XML tags specify what keywords to enable. Unlike for system providers, there are no textual constants defined for event providers, so hexadecimal-style strings must be used. However, the syntax is the same as for system provider. If no keywords are specified, the default value of zero is used (which is treated by ETW as the string 0xFFFFFFFFFFFFFFFF).

Derived event providers have all the attributes of the base provider by default. They can be overridden by explicitly specifying them in the derived provider. For more information, see [Inheritance](inheritance.md).


## Example

The following example defines two event providers.

```xml
<EventProvider
  Id="Win32K-provider"
  Name="Microsoft-Windows-Win32K"
  NonPagedMemory="true"
  Stack="true"> 
  <Keywords>
    <Keyword
      Value="0x240000"/>
  </Keywords>
</EventProvider>

<EventProvider
  Id="Search-Core-provider"
  Name="Microsoft-Windows-Search-Core"/>
```

The following code examples define capture-state providers.

```xml
<EventProvider Id="sample-provider" Name="SampleProvider" NonPagedMemory="true" Level="5">
  <Keywords>
    <Keyword Value="0x98"/> <!-- Provider is enabled with these keywords throughout the tracing session. -->
  </Keywords>
  <CaptureStateOnStart>
    <Keyword Value="0xff4"/> <!-- Provider is enabled with these keywords when tracing is started. -->
  </CaptureStateOnStart>
  <CaptureStateOnSave>
    <Keyword Value="0x118"/> <!-- Provider is enabled with these keywords when tracing is saved. -->
  </CaptureStateOnSave>
</EventProvider>

<EventProvider Id="EventProvider_DWMWin32k_CaptureState" Name="e7ef96be-969f-414f-97d7-3ddb7b558ccc" NonPagedMemory="true" CaptureStateOnly="true" > 
  <!-- CaptureStateOnly="true" means that provider is not enabled throughout the tracing session. -->
  <CaptureStateOnSave>
    <Keyword Value="0x80000"/> <!-- Provider is enabled with these keywords when tracing is saved. -->
  </CaptureStateOnSave>
</EventProvider>
```

For managed scenarios, use the following event provider definition:

```xml
<EventCollectorId Value ="WPAEventCollector">
  <EventProviders>
    <EventProviderId Value="EventProvider_DotNetProvider" />
    <EventProvider Name="Microsoft-Windows-WPA" Id="Microsoft-Windows-WPA" Stack="true">
    </EventProvider>
  </EventProviders>
</EventCollectorId>
```


## Related topics

[Elements](elements.md)

