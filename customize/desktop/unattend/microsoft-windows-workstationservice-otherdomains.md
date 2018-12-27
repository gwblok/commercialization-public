---
title: OtherDomains
description: OtherDomains
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 53821a7d-2599-4af2-a1ae-87e14fb03012
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# OtherDomains


`OtherDomains` specifies the Microsoft LAN Manager domains to be listed for browsing. Multiple domains can be listed, separated by semicolons.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Otherdomains</em></p></td>
<td><p>Specifies Microsoft LAN Manager domains to be listed for browsing. <em>Otherdomains</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

## Parent Hierarchy


[Microsoft-Windows-WorkstationService](microsoft-windows-workstationservice.md) | **OtherDomains**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-WorkstationService](microsoft-windows-workstationservice.md).

## XML Example


The following XML output shows how to specify the Microsoft LAN Manager domains to be listed for browsing.

```
<OtherDomains>domain1.fabrikam.com;domain2.fabrikam.com</OtherDomains>
```

## Related topics


[Microsoft-Windows-WorkstationService](microsoft-windows-workstationservice.md)

 

 







