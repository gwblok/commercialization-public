---
title: HeapProcessIds
description: HeapProcessIds
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bc7619b5-11f7-48d1-93f3-5103fbfc52ce
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# HeapProcessIds

Represents a collection of heap process identifiers.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)&gt;
  * \<[HeapEventProvider](heapeventprovider.md)&gt;
     * \<**HeapProcessIds**&gt;
  * \<[Profiles](profiles.md)&gt;
    * \<[Profile](profile-wpr.md)&gt;
      * \<[Collectors](collectors.md)&gt;
        * \<[HeapEventCollectorId](heapeventcollectorid.md)&gt;
          * \<[HeapEventProviders](heapeventproviders.md)&gt;
            * \<[HeapEventProviderId](heapeventproviderid.md)&gt;
              * \<**HeapProcessIds**&gt;
            * \<[HeapEventProvider](heapeventprovider.md)&gt;
              * \<**HeapProcessIds**&gt;


## Syntax

```
<HeapProcessIds Operation = "Set" | "Add" | “Remove” >

  <!-- Child elements -->
  HeapProcessId

</HeapProcessIds>
```


## Attributes and Elements


### Attributes

| Attribute     | Description                                                          | Data type                                                                                                 | Required | Default |
| :------------ | :------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Operation** | Indicates whether **HeapProcessId** elements should be set or added. | This attribute can have one of the following values: <ul> <li>Set</li> <li>Add</li> <li>Remove</li> </ul> | No       | Set     |


### Child Elements

| Element                           | Description                         | Requirement          |
| :-------------------------------- | :---------------------------------- | :------------------- |
| [HeapProcessId](heapprocessid.md) | Uniquely identifies a heap process. | Required, 1 or more. |


### Parent Elements

| Element                                       | Description                                  |
| :-------------------------------------------- | :------------------------------------------- |
| [HeapEventProvider](heapeventprovider.md)     | Represents a heap event provider.            |
| [HeapEventProviderId](heapeventproviderid.md) | Represents a heap event provider identifier. |


## Related topics

[Elements](elements.md)

