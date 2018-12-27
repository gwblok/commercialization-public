---
title: LmAnnounce
description: LmAnnounce
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4a860959-ffb6-4949-b219-1fc642b12537
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# LmAnnounce


`LmAnnounce` specifies whether a server announces its presence through LanMan (LM) or Net BIOS announcements.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the server sends LanMan (LM) or Net BIOS announcements to notify other computers of its availability.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the server does not send LanMan (LM) or Net BIOS announcements. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-SMBServer](microsoft-windows-smbserver.md) | **LmAnnounce**

## Valid Configuration Passes


generalize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-SMBServer](microsoft-windows-smbserver.md).

## XML Example


The following XML output shows how to specify that the server sends LanMan (LM) or Net BIOS announcements to notify other computers of its availability.

```
<LmAnnounce>true</LmAnnounce>
<Size>2</Size>
```

## Related topics


[Microsoft-Windows-SMBServer](microsoft-windows-smbserver.md)

 

 







