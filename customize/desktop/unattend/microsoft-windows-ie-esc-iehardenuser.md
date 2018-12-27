---
title: IEHardenUser
description: IEHardenUser
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5bd01fc8-0c6e-4e41-99dd-12b2e39ba517
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# IEHardenUser


`IEHardenUser` specifies whether Internet Explorer Enhanced Security Configuration (ESC) is enabled for all users. When Internet Explorer ESC is enabled, it reduces the exposure of your server to potential security attacks from Web pages that do not belong to the Local Intranet zone or the Trusted Sites zone.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that ESC is enabled for all users on the computer. This is the default setting.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that ESC is not enabled for all users on the computer.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-ESC](microsoft-windows-ie-esc.md) | **IEHardenUser**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-ESC](microsoft-windows-ie-esc.md).

## XML Example


The following XML output specifies that ESC is enabled for all users on the computer.

```
<IEHardenUser>true</IEHardenUser>
```

## Related topics


[LocalIntranetSites](microsoft-windows-ie-internetexplorer-localintranetsites.md)

[TrustedSites](microsoft-windows-ie-internetexplorer-trustedsites.md)

[Microsoft-Windows-IE-ESC](microsoft-windows-ie-esc.md)

 

 







