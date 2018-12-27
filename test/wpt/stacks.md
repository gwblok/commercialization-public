---
title: Stacks
description: Stacks
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5ea2e972-ca03-460a-9fed-8eb7670221ac
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# Stacks

Represents a collection of stacks. If the **Operation** attribute is specified, the **Stack** elements can be set or added to the collection.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[Profiles](profiles.md)\>
    * \<[SystemProvider](systemprovider.md)\>
      * \<**Stacks**\>
    * \<[Profile](profile-wpr.md)\>
      * \<[Collectors](collectors.md)\>
        * \<[SystemCollectorId](systemcollectorid.md)\>
          * \<[SystemProviderId](systemproviderid.md)\>
            * \<**Stacks**\>
          * \<[SystemProvider](systemprovider.md)\>
            * \<**Stacks**\>


## Syntax

```
<Stacks Operation = OperationEnumeration>

  <!-- Child elements -->
  Stack

</Stacks>
```


## Attributes and Elements


### Attributes

| Attribute     | Description                                                  | Data type                                                                                                 | Required | Default |
| :------------ | :----------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------- | :------- | :------ |
| **Operation** | Indicates whether **Stack** elements should be set or added. | This attribute can have one of the following values: <ul> <li>Set</li> <li>Add</li> <li>Remove</li> </ul> | No       | Set     |


### Child Elements

| Element               | Description                | Requirement          |
| :-------------------- | :------------------------- | :------------------- |
| [Stack](stack-wpa.md) | Represents a system stack. | Required, 1 or more. |


### Parent Elements

| Element                                 | Description                              |
| :-------------------------------------- | :--------------------------------------- |
| [SystemProvider](systemprovider.md)     | Represents a system provider.            |
| [SystemProviderId](systemproviderid.md) | Represents a system provider identifier. |


## Related topics

[Elements](elements.md)

