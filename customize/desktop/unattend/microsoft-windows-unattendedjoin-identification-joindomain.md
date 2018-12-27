---
title: JoinDomain
description: JoinDomain
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 196de9ea-c3a4-4994-9e68-b3a1d90ff187
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# JoinDomain


`JoinDomain` specifies the name of the domain to join. If this value is set, [JoinWorkgroup](microsoft-windows-unattendedjoin-identification-joinworkgroup.md) cannot be set.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Domain_name</em></p></td>
<td><p>Specifies the name of the domain to join during Windows Setup. <em>Domain_name</em> can be the fully qualified Domain Name System (DNS) name of the domain or the NetBIOS name of the domain. <em>Domain_name</em> is a string.</p>
<p>You can specify either a domain to join or a workgroup to assign by using the <code>JoinDomain</code> or <a href="microsoft-windows-unattendedjoin-identification-joinworkgroup.md" data-raw-source="[JoinWorkgroup](microsoft-windows-unattendedjoin-identification-joinworkgroup.md)">JoinWorkgroup</a> settings respectively. However, only one of these settings should be present in an answer file. If both exist in an answer file, the value for <code>JoinDomain</code> is used, and JoinWorkgroup is ignored.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | **JoinDomain**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example


The following XML output shows how to set the identification credentials.

```
<Identification>
   <Credentials>
      <Domain>fabrikam.com</Domain>
      <Password>MyPassword</Password>
      <Username>MyUserName</Username>
   </Credentials>
   <JoinDomain>fabrikam.com</JoinDomain>
   <MachinePassword>ComputerPassword</MachinePassword>
</Identification>
```

## Related topics


[Identification](microsoft-windows-unattendedjoin-identification.md)

 

 







