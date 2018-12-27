---
title: EventProviderId
description: EventProviderId
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b97422a9-0fa1-484b-9b2e-8fd72dcbf494
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# EventProviderId

Represents an event provider identifier for the profile.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[EventCollectorId](eventcollectorid.md)\>
          * \<[EventProviders](eventproviders.md)\>
            * \<**EventProviderId**\>


## Syntax

```
<EventProviderId Value = IdType>

  <!-- Child elements -->
  Keywords,
  CaptureStateOnStart,
  CaptureStateOnSave

</EventProviderId>
```


## Attributes and Elements


### Attributes

| Attribute | Description                             | Data type                                                                             | Required | Default |
| :-------- | :-------------------------------------- | :------------------------------------------------------------------------------------ | :------- | :------ |
| **Value** | Uniquely identifies the event provider. | String that must have at least one character and cannot contain colons (:) or spaces. | Yes      |         |


### Child Elements

| Element                                                       | Description                                                                                          | Requirement                                                        |
| :------------------------------------------------------------ | :--------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------- |
| [Keywords (in EventProvider)](keywords--in-eventprovider-.md) | Represents a collection of keywords.                                                                 | Required, 1 or more. Use `0x0` as a keyword to include all events. |
| [CaptureStateOnStart](capturestateonstart.md)                 | Represents a collection of keywords that describe events to be captured at the start of a recording. | Optional, zero or 1.                                               |
| [CaptureStateOnSave](capturestateonsave.md)                   | Represents a collection of keywords that describe events to be captured when a recording is saved.   | Optional, zero or 1.                                               |


### Parent Elements

| Element                             | Description                                                                |
| :---------------------------------- | :------------------------------------------------------------------------- |
| [EventProviders](eventproviders.md) | Represents a collection of event providers and event provider identifiers. |


## Example

For managed scenarios, use the following event provider definition.

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

