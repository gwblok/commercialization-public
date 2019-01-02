---
title: Profile
description: Profile
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 92a5d494-cd6f-4a9b-942b-f1318ab48b00
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# Profile

Represents a collection of problem categories and collectors elements.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<**Profile**\>


## Syntax

```
<Profile Id          = IdType
         Name        = string
         Description = string
         Base        = string
         LoggingMode = "File" | "Memory"
         DetailLevel = "Verbose" | "Light"
         Strict      = boolean
         Internal    = boolean
         Default     = boolean>

  <!-- Child elements -->
  ProblemCategories,
  Collectors

</Profile>
```


## Attributes and Elements

### Attributes

| Attribute       | Description                                                                                                                                                                                                                                                                                                                                                                                                                               | Data type                                                                                       | Required | Default |
| :-------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------- | :------- | :------ |
| **Id**          | Uniquely identifies the profile.                                                                                                                                                                                                                                                                                                                                                                                                          | String that must have at least one character and cannot contain colons or spaces.               | Yes      |         |
| **Name**        | Indicates the name of the profile.                                                                                                                                                                                                                                                                                                                                                                                                        | string                                                                                          | Yes      |         |
| **Description** | Indicates the description of the profile.                                                                                                                                                                                                                                                                                                                                                                                                 | string                                                                                          | Yes      |         |
| **Base**        | Indicates the base of the profile.                                                                                                                                                                                                                                                                                                                                                                                                        | string                                                                                          | No       |         |
| **LoggingMode** | Indicates whether WPR writes to memory or to a sequential file.                                                                                                                                                                                                                                                                                                                                                                           | This attribute can have one of the following values: <ul> <li>File</li> <li>Memory</li> </ul>   | Yes      | File    |
| **DetailLevel** | Specifies whether a profile definition is used for timing tracing (`Light`) or analysis tracing (`Verbose`).                                                                                                                                                                                                                                                                                                                              | This attribute can have one of the following values: <ul> <li>Verbose</li> <li>Light</li> </ul> | Yes      | Verbose |
| **Strict**      | Indicates whether the failure of a provider or collector causes the start operation fail. If this attribute is set to `false`, the start operation succeeds even if some collectors or providers fail. At least one collector and one provider must succeed for the operation to continue. If this attribute is set to `true`, information about providers or collectors that failed to start is provided as warnings, instead of errors. | boolean                                                                                         | No       | false   |
| **Internal**    | Indicates whether the profile is internal.                                                                                                                                                                                                                                                                                                                                                                                                | boolean                                                                                         | No       | false   |
| **Default**     | Indicates whether the profile is a default profile.                                                                                                                                                                                                                                                                                                                                                                                       | boolean                                                                                         | No       | false   |


### Child Elements

| Element                                   | Description                                            | Requirement          |
| :---------------------------------------- | :----------------------------------------------------- | :------------------- |
| [ProblemCategories](problemcategories.md) | Represents a collection of problem categories.         | Required, exactly 1. |
| [Collectors](collectors.md)               | Represents a collection of collectors for the profile. | Required, exactly 1. |
| [TraceMergeProperties](tracemergeproperties.md) | Represents a collection of trace merge properites. | Optional, exactly 1. |


### Parent Elements

| Element                 | Description                                                    |
| :---------------------- | :------------------------------------------------------------- |
| [Profiles](profiles.md) | Represents a collection of collectors, providers and profiles. |


## Remarks

Each .wprp file typically contains at least two profile definitions: one for each logging mode. The exception is that on/off transition profiles can be logged only to file, so the .wprp file for those profiles can contain only one profile definition. Each .wprp file can contain at most four profiles: one for each combination of logging mode and detail level. All profiles in a single .wprp file must have the same value for the **Name** attribute.

Construct the **Id** attribute value by combining the values of the **Name**, **DetailLevel**, and **LoggingMode** attributes, separated by periods, as shown in the following example.

Derived profiles have all the attributes of the base profile by default. These can be overridden by explicitly specifying them in the derived profile. For more information, see [Inheritance](inheritance.md).


## Example

The following code example shows a profile definition.

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
    <EventCollectorId
      Value="WPREventCollector">
      <EventProviders>
        <EventProviderId
          Value="Win32K-provider"/>
        <EventProviderId
          Value="Search-Core-provider"/>
      </EventProviders>
    </EventCollectorId>
  </Collectors>
</Profile>
```

Collectors and providers can also be defined in place, inside the profile definition.


## Related topics

[Elements](elements.md)

