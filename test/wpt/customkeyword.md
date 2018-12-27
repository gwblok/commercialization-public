---
title: CustomKeyword
description: CustomKeyword
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 776e6349-4d19-44a9-b49a-a2c73e218540
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# CustomKeyword


Represents a custom keyword for the profile.

## Element Hierarchy


* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[SystemProvider](systemprovider.md)\>
      * \<[Keywords (in SystemProvider)](keywords--in-systemprovider-.md)\>
        * \<**CustomKeyword**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[SystemCollectorId](systemcollectorid.md)\>
          * \<[SystemProvider](systemprovider.md)\>
            * \<[Keywords (in SystemProvider)](keywords--in-systemprovider-.md)\>
              * \<**CustomKeyword**\>

## Syntax


```
<CustomKeyword Value = SystemCustomKeywordAttributeType>
</CustomKeyword>
```

## Attributes and Elements


### Attributes

| Attribute              | Description                                           | Data type                                                    | Required | Default |
|:-----------------------|:------------------------------------------------------|:-------------------------------------------------------------|:---------|:--------|
| <strong>Value</strong> | The hexadecimal-form string name of the custom event. | String built with the following pattern: 0x[a-fA-F0-9]{1,8}. | Yes      |         |


### Child Elements

None.


### Parent Elements

| Element                                                         | Description                                              |
|:----------------------------------------------------------------|:---------------------------------------------------------|
| [Keywords (in SystemProvider)](keywords--in-systemprovider-.md) | Represents a collection of keywords and custom keywords. |


## Remarks

This element enables creation of a custom keyword for any possible Event Tracing for Windows (ETW) event.


## Related topics

[Elements](elements.md)

