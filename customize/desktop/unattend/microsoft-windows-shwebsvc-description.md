---
title: Description
description: Description
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: cbf06de9-ea77-4a39-bf15-7eed24e79d42
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Description


`Description` specifies the description of the online printing company to display in the Online Print Wizard.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Specifies the description of the online printing company to display in the Online Print Wizard. <em>Description</em> is a string with a maximum length of 80 characters.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-shwebsvc](microsoft-windows-shwebsvc.md) | **Description**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-shwebsvc](microsoft-windows-shwebsvc.md).

## XML Example


The following XML output shows how to set Lucerne Publishing for online printing.

```
<Description>Get photos printed by Lucerne and delivered to your home.</Description>
<DisplayName>Lucerne Publishing</DisplayName>
<href>lucernepublishing.com</href>
<Icon>c:\Lucerne\lucernepub.ico</Icon>
<ID>lucernepub</ID>
```

## Related topics


[Microsoft-Windows-shwebsvc](microsoft-windows-shwebsvc.md)

 

 







