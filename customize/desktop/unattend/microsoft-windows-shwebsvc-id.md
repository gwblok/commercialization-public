---
title: ID
description: ID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b6651dfa-65eb-4f26-8ee5-70d052e19886
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ID


`ID` specifies the identity of the default online printing company in the Online Print Wizard.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>ID</em></p></td>
<td><p>Specifies the identity of the online printing company. This ID is not displayed to the end user. <em>ID</em> is a string with a minimum length of 1 character and a maximum length of 20 characters.</p>
<p>This string must be unique for each service provider.</p>
<p>We recommended that the service provider name, without spaces, be used as the string ID.</p>
<p>For service providers that are managed through the Microsoft Service Provider server, an ID string is assigned.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-shwebsvc](microsoft-windows-shwebsvc.md) | **ID**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-shwebsvc](microsoft-windows-shwebsvc.md).

## XML Example


The following XML output shows how to set Lucerne Publishing for online printing.

```
<Description>Get photos printed by Lucerne and delivered to your home.</Description>
<DisplayName>Lucerne Publishing</DisplayName>
<href>lucernepublishing.com</href>
<Icon>c:\Lucerne\lucernepub.ico</Icon>
<ID>lucernepublishing</ID>
```

## Related topics


[Microsoft-Windows-shwebsvc](microsoft-windows-shwebsvc.md)

 

 







