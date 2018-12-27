---
title: NotInOOBE
description: NotInOOBE
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 17f04477-6154-4567-b02d-c0a88a2a89eb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# NotInOOBE


`NotInOOBE` hides mobile broadband devices or networks in OOBE. You can use this setting if you have a mobile device with embedded mobile broadband that’s sold with a deactivated mobile operator SIM. In this case, the mobile operator requires the mobile broadband device to be hidden in OOBE because SIM activation requires use of a mobile operator account experience app or a web browser, which are not supported in OOBE.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Hides mobile broadband category in OOBE.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Displays mobile broadband category in OOBE. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-WwanUI](microsoft-windows-wwanui.md) | **NotInOOBE**

## Applies To


For a full list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-WwanUI](microsoft-windows-wwanui.md).

## XML Example


The following XML output shows how to hide the mobile broadband category in OOBE.

```
<NotInOOBE>true</NotInOOBE>
```

## Related topics


[Microsoft-Windows-WwanUI](microsoft-windows-wwanui.md)

 

 







