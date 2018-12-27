---
title: PublicProfile\_EnableFirewall
description: PublicProfile\_EnableFirewall
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: dae3a90b-76c4-43f6-bde8-84e132369a8f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PublicProfile\_EnableFirewall


`PublicProfile_EnableFirewall` enables Windows Firewall for the public profile.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Enables Windows Firewall. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Disables Windows Firewall.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Networking-MPSSVC-Svc](networking-mpssvc-svc.md) | **PublicProfile\_EnableFirewall**

## Valid Configuration Passes


specialize

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Networking-MPSSVC-Svc](networking-mpssvc-svc.md).

## XML Example


The following XML output shows how to disable Windows Firewall.

```
<DomainProfile_EnableFirewall>false</DomainProfile_EnableFirewall>
<PrivateProfile_EnableFirewall>false</PrivateProfile_EnableFirewall>
<PublicProfile_EnableFirewall>false</PublicProfile_EnableFirewall>
```

## Related topics


[Networking-MPSSVC-Svc](networking-mpssvc-svc.md)

 

 







