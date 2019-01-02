---
title: OEMName
description: OEMName
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6fbac8c8-9b94-4039-9cb6-22fb69371423
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# OEMName


`OEMName` specifies the name of the Original Equipment Manufacturer (OEM) for the group or groups of app tiles that you pin to the Start screen.

This value will be appended with the word "apps", or the local equivalent, on the Start screen.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>&lt;OEM_name&gt;</em></p></td>
<td><p>Specifies the name of the OEM. <em>&lt;OEM_name&gt;</em> is a string with a maximum length of 256 characters.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **OEMName**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to set the OEM name. On the Start screen, the group of Start Tiles created by the OEM appears with the heading: "Fabrikam apps".

```
<OEMName>Fabrikam</OEMName>
```

## Related topics


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)

[StartTiles](microsoft-windows-shell-setup-starttiles.md)

[Manufacturer](microsoft-windows-shell-setup-oeminformation-manufacturer.md)

[Manufacturer](microsoft-windows-helpandsupport-helpandsupport-manufacturer.md)

 

 







