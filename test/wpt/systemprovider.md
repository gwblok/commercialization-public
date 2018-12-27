---
title: SystemProvider
description: SystemProvider
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 20262ec7-6b20-42cb-903f-1db57a9f1e58
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# SystemProvider

Describes the configuration to enable the kernel-mode provider. The system provider definition specifies what system keywords, stacks, and pool tags to enable.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<**SystemProvider**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[SystemCollectorId](systemcollectorid.md)\>
          * \<**SystemProvider**\>


## Syntax

```
<SystemProvider Id   = IdType
                Base = string>

  <!-- Child elements -->
  Keywords,
  Stacks,
  PoolTags

</SystemProvider>
```


## Attributes and Elements


### Attributes

| Attribute | Description                                                                                                                                                                                          | Data type                                                                             | Required | Default |
| :-------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------ | :------- | :------ |
| **Id**    | Uniquely identifies the system provider.                                                                                                                                                             | String that must have at least one character and cannot contain colons (:) or spaces. | Yes      |         |
| **Base**  | Indicates the base of the system provider. Derived providers have all the attributes of the base provider by default. These can be overridden by explicitly specifying them in the derived provider. | string                                                                                | No       |         |


### Child Elements

| Element                                                         | Description                                              | Requirement          |
| :-------------------------------------------------------------- | :------------------------------------------------------- | :------------------- |
| [Keywords (in SystemProvider)](keywords--in-systemprovider-.md) | Represents a collection of keywords and custom keywords. | Required, exactly 1. |
| [Stacks](stacks.md)                                             | Represents a collection of stacks.                       | Required, exactly 1. |
| [PoolTags](pooltags.md)                                         | Represents a collection of pool tags.                    | Required, exactly 1. |


### Parent Elements

| Element                                   | Description                                                     |
| :---------------------------------------- | :-------------------------------------------------------------- |
| [Profiles](profiles.md)                   | Represents a collection of collectors, providers, and profiles. |
| [SystemCollectorId](systemcollectorid.md) | Represents a system collector identifier.                       |


## Remarks

For information about how to define pool tags, see [PoolTag](pooltag.md).


## Example

```xml
<SystemProvider Id="system-provider">
  <Keywords>
    <Keyword Value="ProcessThread"/>
    <Keyword Value="Loader"/>
    <Keyword Value="CSwitch"/>
  </Keywords>
  <Stacks>
    <Stack Value="ThreadCreate"/>
    <Stack Value="ReadyThread"/>
    <Stack Value="CSwitch"/>
  </Stacks>
  <PoolTags>
    <PoolTag Value="a*"/>
    <PoolTag Value="b*"/> 
    <PoolTag Value="c*"/> 
    <PoolTag Value="d*"/> 
  </PoolTags>
</SystemProvider>
```


## Related topics

[Elements](elements.md)

