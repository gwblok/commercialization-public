---
title: DisableStatefulFTP
description: DisableStatefulFTP
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e745e752-5abb-4d16-a941-0aeb5c552fea
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisableStatefulFTP


`DisableStatefulFTP` disables the Windows Firewall File Transfer Protocol (FTP) connection inspection engine.

## Values


For server editions of Windows:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Disables FTP connection inspection. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Enables FTP connection inspection.</p></td>
</tr>
</tbody>
</table>

 

For client editions of Windows and for Windows RT 8.1:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Disables FTP connection inspection.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Enables FTP connection inspection. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Networking-MPSSVC-Svc](networking-mpssvc-svc.md) | **DisableStatefulFTP**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Networking-MPSSVC-Svc](networking-mpssvc-svc.md).

## XML Example


The following XML output shows how to set Windows Firewall.

```
<DisableStatefulFTP>true</DisableStatefulFTP>
<DisableStatefulPPTP>true</DisableStatefulPPTP>
<DomainProfile_DisableNotifications>true</DomainProfile_DisableNotifications>
<DomainProfile_LogDroppedPackets>true</DomainProfile_LogDroppedPackets>
<DomainProfile_LogFile>C:\\MyLogFile.log</DomainProfile_LogFile>
<DomainProfile_LogFileSize>8192</DomainProfile_LogFileSize>
<DomainProfile_LogSuccessfulConnections>true</DomainProfile_LogSuccessfulConnections>
<PrivateProfile_DisableNotifications>true</PrivateProfile_DisableNotifications>
<PrivateProfile_LogDroppedPackets>true</PrivateProfile_LogDroppedPackets>
<PrivateProfile_LogFile>C:\\MyLogFile.log</PrivateProfile_LogFile>
<PrivateProfile_LogFileSize>8192</PrivateProfile_LogFileSize>
<PrivateProfile_LogSuccessfulConnections>true</PrivateProfile_LogSuccessfulConnections>
<PublicProfile_DisableNotifications>true</PublicProfile_DisableNotifications>
<PublicProfile_LogDroppedPackets>true</PublicProfile_LogDroppedPackets>
<PublicProfile_LogFile>C:\\MyLogFile.log</PublicProfile_LogFile>
<PublicProfile_LogFileSize>8192</PublicProfile_LogFileSize>
<PublicProfile_LogSuccessfulConnections>true</PublicProfile_LogSuccessfulConnections>
```

## Related topics


[Networking-MPSSVC-Svc](networking-mpssvc-svc.md)

 

 







