---
title: MachineObjectOU
description: MachineObjectOU
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0820e49f-3ae2-4175-8ea2-1fb0a8fca5a6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# MachineObjectOU


`MachineObjectOU` is an optional setting. It specifies the Lightweight Directory Access Protocol (LDAP) X 500-distinguished name of the organizational unit (OU) in which the computer account is created. This account is in Active Directory on a domain controller in the domain to which the computer is being joined.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>MachineObjectOU</em></p></td>
<td><p>Specifies the full LDAP path name of the OU to which the computer belongs. For example,</p>
<p><code>OU=MyOu,DC=MyDom,DC=MyCompany,DC=com</code></p>
<p><em>MachineObjectOU</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | **MachineObjectOU**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example


The following XML output shows how to set the OU.

```
<MachineObjectOU>OU=MyOu,OU=MyParentOu,DC=MyDomain,DC=MyCompany,DC=com</MachineObjectOU>
```

## Related topics


[Identification](microsoft-windows-unattendedjoin-identification.md)

 

 







