---
title: UnsecureJoin
description: UnsecureJoin
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c0d4b51c-3e13-4ba8-aa43-a2392bc33c66
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# UnsecureJoin


`UnsecureJoin` specifies whether to add the computer to the domain without requiring a unique password. `UnsecureJoin` is performed, by using a null session with a pre-existing account. This means there is no authentication to the domain controller when configuring the machine account; it is done anonymously. The account must have a well-known password or a specified value for [MachinePassword](microsoft-windows-unattendedjoin-identification-machinepassword.md). The well-known password is the first 14 characters of the computer name in lower case. For more information, see MachinePassword. If the well-known password is used, then the password is changed to a strong password by Netlogon after the join completes.

**Note**  
If `UnsecureJoin` is enabled, do not create settings for [Domain](microsoft-windows-unattendedjoin-identification-credentials-domain.md), [Username](microsoft-windows-unattendedjoin-identification-credentials-username.md), or [Password](microsoft-windows-unattendedjoin-identification-credentials-password.md).

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Adds the computer to the domain without requiring that <a href="microsoft-windows-unattendedjoin-identification-credentials-domain.md" data-raw-source="[Domain](microsoft-windows-unattendedjoin-identification-credentials-domain.md)">Domain</a>, <a href="microsoft-windows-unattendedjoin-identification-credentials-username.md" data-raw-source="[Username](microsoft-windows-unattendedjoin-identification-credentials-username.md)">Username</a>, and <a href="microsoft-windows-unattendedjoin-identification-credentials-password.md" data-raw-source="[Password](microsoft-windows-unattendedjoin-identification-credentials-password.md)">Password</a> are specified in the Credentials section for authentication to the domain during the domain join process.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Requires that a valid <a href="microsoft-windows-unattendedjoin-identification-credentials-domain.md" data-raw-source="[Domain](microsoft-windows-unattendedjoin-identification-credentials-domain.md)">Domain</a>, <a href="microsoft-windows-unattendedjoin-identification-credentials-username.md" data-raw-source="[Username](microsoft-windows-unattendedjoin-identification-credentials-username.md)">Username</a>, and <a href="microsoft-windows-unattendedjoin-identification-credentials-password.md" data-raw-source="[Password](microsoft-windows-unattendedjoin-identification-credentials-password.md)">Password</a> are specified in the <a href="microsoft-windows-unattendedjoin-identification-credentials.md" data-raw-source="[Credentials](microsoft-windows-unattendedjoin-identification-credentials.md)">Credentials</a> section for authentication to the domain during the domain join process. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
[Domain](microsoft-windows-unattendedjoin-identification-credentials-domain.md), [Username](microsoft-windows-unattendedjoin-identification-credentials-username.md), and [Password](microsoft-windows-unattendedjoin-identification-credentials-password.md) must not be specified in the Credentials section if `UnsecureJoin` is set to true.

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | **UnsecureJoin**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example


The following XML output shows the computer added to the domain without the requirement of a unique password.

```
<UnsecureJoin>true</UnsecureJoin>
```

## Related topics


[Identification](microsoft-windows-unattendedjoin-identification.md)

 

 







