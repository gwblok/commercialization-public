---
title: SystemProviderId
description: SystemProviderId
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f5ac9900-e43b-480b-9be7-5f5f726b1635
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# SystemProviderId

Uniquely identifies the system provider.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<**SystemProviderId**\>


## Syntax

```
<SystemProviderId Value = IdType>

  <!-- Child elements -->
  Keywords,
  Stacks,
  PoolTags

</SystemProviderId>
```


## Attributes and Elements


### Attributes

| Attribute | Description                              | Data type                                                                             | Required | Default |
| :-------- | :--------------------------------------- | :------------------------------------------------------------------------------------ | :------- | :------ |
| **Value** | Uniquely identifies the system provider. | String that must have at least one character and cannot contain colons (:) or spaces. | Yes      |         |


### Child Elements

| Element                                                         | Description                                          | Requirement          |
| :-------------------------------------------------------------- | :--------------------------------------------------- | :------------------- |
| [Keywords (in SystemProvider)](keywords--in-systemprovider-.md) | Represents a collection of system provider keywords. | Required, exactly 1. |
| [Stacks](stacks.md)                                             | Represents a collection of stacks.                   | Required, exactly 1. |
| [PoolTags](pooltags.md)                                         | Represents a collection of pool tags.                | Required, exactly 1. |


### Parent Elements

| Element                     | Description                                                                                                                            |
| :-------------------------- | :------------------------------------------------------------------------------------------------------------------------------------- |
| [Collectors](collectors.md) | Represents a collection of system collector identifiers, event collector identifiers, and optionally heap event collector identifiers. |


## Remarks

For more information about authoring system provider definitions, see [2. System and Event Provider Definitions](2-system-and-event-provider-definitions.md) and [3. Profile Definitions](3-profile-definitions.md).


## Example

The following code example shows the section of a profile definition that contains this element.

```xml
<Profile
  Id="Example.Light.File"
  Name="Example"
  DetailLevel="Light"
  LoggingMode="File"
  Description="Example profile">
  <ProblemCategories> 
    <ProblemCategory
      Value="First Level Triage"/>
  </ProblemCategories> 
  <Collectors>
    <SystemCollectorId
      Value="WPRSystemCollector">
      <SystemProviderId
        Value="system-provider"/>
    </SystemCollectorId>
…
  </Collectors>
</Profile>
```


## Related topics

[Elements](elements.md)

