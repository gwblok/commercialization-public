---
title: Keyword (in EventProvider)
description: Keyword (in EventProvider)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f5b18ec2-8b85-40d6-ac69-91ccd7e7fad9
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# Keyword (in EventProvider)

Describes the Event Tracing for Windows (ETW) keyword for a user-mode provider.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[EventProvider](eventprovider.md)\>
      * \<[Keywords (in EventProvider)](keywords--in-eventprovider-.md)\>
        * \<**Keyword (in EventProvider)**\>
      * \<[CaptureStateOnStart](capturestateonstart.md)\>
        * \<**Keyword (in EventProvider)**\>
      * \<[CaptureStateOnSave](capturestateonsave.md)\>
        * \<**Keyword (in EventProvider)**\>
    * \<[HeapEventProvider](heapeventprovider.md)\>
      * \<[Keywords (in EventProvider)](keywords--in-eventprovider-.md)\>
        * \<**Keyword (in EventProvider)**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[EventCollectorId](eventcollectorid.md)\>
          * \<[EventProviders](eventproviders.md)\>
            * \<[EventProviderId](eventproviderid.md)\>
              * \<[Keywords (in EventProvider)](keywords--in-eventprovider-.md)\>
                * \<**Keyword (in EventProvider)**\>
            * \<[EventProvider](eventprovider.md)\>
              * \<[Keywords (in EventProvider)](keywords--in-eventprovider-.md)\>
                * \<**Keyword (in EventProvider)**\>
              * \<[CaptureStateOnStart](capturestateonstart.md)\>
                * \<**Keyword (in EventProvider)**\>
              * \<[CaptureStateOnSave](capturestateonsave.md)\>
                * \<**Keyword (in EventProvider)**\>
        * \<[HeapEventCollectorId](heapeventcollectorid.md)\>
          * \<[HeapEventProviders](heapeventproviders.md)\>
            * \<[HeapEventProviderId](heapeventproviderid.md)\>
              * \<[Keywords (in EventProvider)](keywords--in-eventprovider-.md)\>
                * \<**Keyword (in EventProvider)**\>
            * \<[HeapEventProvider](heapeventprovider.md)\>
              * \<[Keywords (in EventProvider)](keywords--in-eventprovider-.md)\>
                * \<**Keyword (in EventProvider)**\>


## Syntax

```
<Keyword Value string
</Keyword>
```


## Attributes and Elements


### Attributes

| Attribute | Description                               | Data type | Required | Default |
| :-------- | :---------------------------------------- | :-------- | :------- | :------ |
| **Value** | String that is the name of the ETW event. | string    | Yes      |         |


### Child Elements

None.


### Parent Elements

| Element                                                       | Description                                         |
| :------------------------------------------------------------ | :-------------------------------------------------- |
| [Keywords (in EventProvider)](keywords--in-eventprovider-.md) | Represents a collection of event provider keywords. |


## Related topics

[Elements](elements.md)

