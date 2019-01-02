---
title: DomainProfile\_LogFileSize
description: DomainProfile\_LogFileSize
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6b5bba95-e9f9-4797-a003-e21218b39db9
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DomainProfile\_LogFileSize


`DomainProfile_LogFileSize` specifies the size of the default log file for Windows Firewall for the domain profile.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>LogFileSize</em></p></td>
<td><p>Specifies the default log file size. <em>LogFileSize</em> is an integer with a default value of <strong>4096</strong> (4 MB).</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Networking-MPSSVC-Svc](networking-mpssvc-svc.md) | **DomainProfile\_LogFileSize**

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

 

 







