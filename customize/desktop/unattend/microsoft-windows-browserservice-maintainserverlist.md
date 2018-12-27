---
title: MaintainServerList
description: MaintainServerList
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 919872be-6475-4947-aa22-2bfc0f9ee26c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# MaintainServerList


`MaintainServerList` specifies whether the computer can act as a master or backup browser on a subnet.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Yes</strong></p></td>
<td><p>Specifies that the computer becomes a master or backup browser.</p></td>
</tr>
<tr class="even">
<td><p><strong>No</strong></p></td>
<td><p>Specifies that the computer cannot become a master or backup browser.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Auto</strong></p></td>
<td><p>Specifies that the computer can become a master or backup browser if needed—that is, if there is no master browser on the subnet or there are not enough master browsers on the subnet. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-BrowserService](microsoft-windows-browserservice.md) | **MaintainServerList**

## Valid Configuration Passes


generalize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-BrowserService](microsoft-windows-browserservice.md).

## XML Example


The following XML output specifies that the computer cannot act as a master or backup browser.

```
<MaintainServerList>No</MaintainServerList>
```

## Related topics


[Microsoft-Windows-BrowserService](microsoft-windows-browserservice.md)

 

 







