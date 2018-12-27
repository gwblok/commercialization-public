---
title: CaptureStateOnSave
description: CaptureStateOnSave
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d672f309-e038-4c69-9288-fbf8e251dfc5
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# CaptureStateOnSave

Represents a collection of keywords that describe events to be captured when a trace is saved. The library requests the provider to log its state information when the collector is saved. If the **Operation** attribute is specified, the **Keyword** elements can be set or added to the collection.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[EventProvider](eventprovider.md)\>
      * \<**CaptureStateOnSave**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[EventCollectorId](eventcollectorid.md)\>
          * \<[EventProviderId](eventproviderid.md)\>
            * \<**CaptureStateOnSave**\>
          * \<[EventProvider](eventprovider.md)\>
            * \<**CaptureStateOnSave**\>


## Syntax

```
<CaptureStateOnSave Operation = "Set" | "Add"> | “Remove”

  <!-- Child elements -->
  Keyword

</CaptureStateOnSave>
```


## Attributes and Elements


### Attributes

| Attribute     | Description                                        | Data type                                                                                                 | Required | Default |
| :------------ | :------------------------------------------------- | :-------------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Operation** | Indicates whether keywords should be set or added. | This attribute can have one of the following values: <ul> <li>Set</li> <li>Add</li> <li>Remove</li> </ul> | No       | Set     |


### Child Elements

| Element                                                     | Description                                                                     | Requirement            |
|:------------------------------------------------------------|:--------------------------------------------------------------------------------|:-----------------------|
| [Keyword (in EventProvider)](keyword--in-eventprovider-.md) | Describes the Event Tracing for Windows (ETW) keyword for a user-mode provider. | Required, one or more. |


### Parent Elements

| Element                               | Description                                   |
|:--------------------------------------|:----------------------------------------------|
| [EventProvider](eventprovider.md)     | Represents an event provider for the profile. |
| [EventProviderId](eventproviderid.md) | Represents an event provider identifier.      |


## Example

The following code example shows how this element is used.

```xml
<EventProvider Id="EventProvider_DWMWin32k_CaptureState" Name="e7ef96be-969f-414f-97d7-3ddb7b558ccc" NonPagedMemory="true" CaptureStateOnly="true" > 
  <!-- CaptureStateOnly="true" means provider is not enabled throughout the tracing session. -->
  <CaptureStateOnSave>
    <Keyword Value="0x80000"/> <!-- Provider is enabled with these keywords when tracing is saved. -->
  </CaptureStateOnSave>
</EventProvider>
```


## Related topics

[Elements](elements.md)

[CustomKeyword](customkeyword.md)

[CaptureStateOnStart](capturestateonstart.md)

