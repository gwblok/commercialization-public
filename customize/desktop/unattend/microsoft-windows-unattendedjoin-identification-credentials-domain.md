---
title: Domain
description: Domain
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c9d10f39-6c99-4586-9c36-2fdb8169638e
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Domain


`Domain` specifies the name of the domain used for an account authentication. `Domain` is used to authenticate an account before the computer can be joined to a domain during Windows Setup.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Domain_name</em></p></td>
<td><p>Specifies the name of the domain used to authenticate an account. <em>Domain_name</em> is a string. The value may be either a fully qualified DNS domain name or a NetBIOS domain name.</p>
<p>If a value for <code>Domain</code> is not specified, <a href="microsoft-windows-unattendedjoin-identification-credentials-username.md" data-raw-source="[Username](microsoft-windows-unattendedjoin-identification-credentials-username.md)">Username</a> must use the user principal name (UPN) format (user<xref href="fully-qualified-DNS-domain)" data-throw-if-not-resolved="False" data-raw-source="@fully-qualified-DNS-domain)"></xref>, NetBIOS-domain\username format, or the fully-qualified-DNS-domain\username format.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | [Credentials](microsoft-windows-unattendedjoin-identification-credentials.md) | **Domain**

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


[Credentials](microsoft-windows-unattendedjoin-identification-credentials.md)

 

 







