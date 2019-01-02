---
title: EventProviders
description: EventProviders
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a486a6e7-56b9-4458-8b7d-23024b3b7762
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# EventProviders

Represents a collection of event provider identifiers and event providers.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[EventCollectorId](eventcollectorid.md)\>
          * \<**EventProviders**\>


## Syntax

```
<EventProviders Operation = "Set" | "Add" | “Remove”>

  <!-- Child elements -->
  EventProviderId,
  EventProvider

</EventProviders>
```


## Attributes and Elements


### Attributes

| Attribute     | Description                                               | Data type                                                                                             | Required | Default |
| :------------ | :-------------------------------------------------------- | :---------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Operation** | Indicates whether event providers should be set or added. | This attribute can have one of the following values: <ul><li>Set</li><li>Add</li><li>Remove</li></ul> | No       | Set     |


### Child Elements

| Element                               | Description                              | Requirement             |
| :------------------------------------ | :--------------------------------------- | :---------------------- |
| [EventProviderId](eventproviderid.md) | Represents an event provider identifier. | Optional, zero or more. |
| [EventProvider](eventprovider.md)     | Represents an event provider.            | Optional, zero or more. |


### Parent Elements

| Element                                 | Description                               |
| :-------------------------------------- | :---------------------------------------- |
| [EventCollectorId](eventcollectorid.md) | Represents an event collector identifier. |


## Example

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

