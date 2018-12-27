---
title: SyncDomainWithMembership
description: SyncDomainWithMembership
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: aff71f9f-6323-4ee9-8e32-6940667502a5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SyncDomainWithMembership


`SyncDomainWithMembership` specifies whether the primary Domain Name Service (DNS) suffix changes when domain membership changes.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the primary DNS suffix does change when domain membership changes. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the primary DNS suffix does not change when domain membership changes.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-WorkstationService](microsoft-windows-workstationservice.md) | **SyncDomainWithMembership**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-WorkstationService](microsoft-windows-workstationservice.md).

## XML Example


The following XML output shows how to specify that the primary Domain Name Service (DNS) suffix does not change when domain membership changes.

```
<SyncDomainWithMembership>false</SyncDomainWithMembership>
```

## Related topics


[Microsoft-Windows-WorkstationService](microsoft-windows-workstationservice.md)

 

 







