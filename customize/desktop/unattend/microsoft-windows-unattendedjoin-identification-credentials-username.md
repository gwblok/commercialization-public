---
title: Username
description: Username
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7bbed9a8-ce6d-4054-9b18-99d39d31d5c0
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Username


`Username` specifies the name of the user account with permission to add the computer to a domain during Windows Setup.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>User_name</em></p></td>
<td><p>Specifies the name of the user account with permission to create a computer account in a domain or to use an existing computer account in a domain. <em>User_name</em> is a string.</p>
<p>The value for <em>Username</em> can be in user principal name (UPN) format (user<xref href="fully_qualified_DNS_domain_name)" data-throw-if-not-resolved="False" data-raw-source="@fully_qualified_DNS_domain_name)"></xref>, domain\username format, or fully-qualified-DNS-domain\username format. If any of these formats is specified, the <a href="microsoft-windows-unattendedjoin-identification-credentials-domain.md" data-raw-source="[Domain](microsoft-windows-unattendedjoin-identification-credentials-domain.md)">Domain</a> setting must be excluded.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | [Credentials](microsoft-windows-unattendedjoin-identification-credentials.md) | **Username**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

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


[Credentials](microsoft-windows-unattendedjoin-identification-credentials.md)

 

 







