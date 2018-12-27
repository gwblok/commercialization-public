---
title: Keywords (in EventProvider)
description: Keywords (in EventProvider)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9ecdbe0a-7635-416a-a690-cf18c63d429f
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# Keywords (in EventProvider)

Represents a collection of event keywords.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[EventProvider](eventprovider.md)\>
      * \<**Keywords (in EventProvider)**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[EventCollectorId](eventcollectorid.md)\>
          * \<[EventProviders](eventproviders.md)\>
            * \<[EventProviderId](eventproviderid.md)\>
              * \<**Keywords (in EventProvider)**\>
            * \<[EventProvider](eventprovider.md)\>
              * \<**Keywords (in EventProvider)**\>


## Syntax

```
<Keywords Operation = "Set" | "Add" | “Remove” >

  <!-- Child elements -->
  Keyword

</Keywords>
```


## Attributes and Elements


### Attributes

| Attribute     | Description                                        | Data type                                                                                                 | Required | Default |
| :------------ | :------------------------------------------------- | :-------------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Operation** | Indicates whether keywords should be set or added. | This attribute can have one of the following values: <ul> <li>Set</li> <li>Add</li> <li>Remove</li> </ul> | No       | Set     |


### Child Elements

| Element                                                     | Description                                                                     | Requirement          |
| :---------------------------------------------------------- | :------------------------------------------------------------------------------ | :------------------- |
| [Keyword (in EventProvider)](keyword--in-eventprovider-.md) | Describes the Event Tracing for Windows (ETW) keyword for a user-mode provider. | Required, 1 or more. |


### Parent Elements

| Element                               | Description                                   |
| :------------------------------------ | :-------------------------------------------- |
| [EventProvider](eventprovider.md)     | Represents an event provider for the profile. |
| [EventProviderId](eventproviderid.md) | Represents an event provider identifier.      |


## Related topics

[Elements](elements.md)

