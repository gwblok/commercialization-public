---
title: DomainProfile\_LogFile
description: DomainProfile\_LogFile
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 977e6009-d898-453d-81e0-c989ef2b5b4d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DomainProfile\_LogFile


`DomainProfile_LogFile` specifies the default log file for Windows Firewall for the domain profile.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>LogFilePathAndName</em></p></td>
<td><p>Specifies the default log file. <em>LogFilePathAndName</em> is a string. The default value is <code>D:\Windows\system32\LogFiles\Firewall\pfirewall.log</code>.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Networking-MPSSVC-Svc](networking-mpssvc-svc.md) | **DomainProfile\_LogFile**

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

 

 







