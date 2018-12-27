---
title: MachinePassword
description: MachinePassword
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 24489f22-ceb8-48ab-90d9-9ef92f8a0e29
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# MachinePassword


`MachinePassword `is used with [UnsecureJoin](microsoft-windows-unattendedjoin-identification-unsecurejoin.md), which is performed by using a null session with a pre-existing account. This means there is no authentication to the domain controller when configuring the computer account. It is done anonymously. The account must have a well-known password or a specified `MachinePassword`. The well-known password is the first 14 characters of the computer name in lowercase.

This setting is valid only if [UnsecureJoin](microsoft-windows-unattendedjoin-identification-unsecurejoin.md) is set to **true**.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>MachinePassword</em></p></td>
<td><p>Specifies the value of the unique password for the computer. <em>MachinePassword</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | **MachinePassword**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example


The following XML output shows how to specify the value of the unique password for the computer.

```
<Identification>
   <Credentials>
      <Domain>fabrikam.com</Domain>
      <Password>MyPassword</Password>
      <Username>MyUserName</Username>
   </Credentials>
   <JoinDomain>fabrikam.com</JoinDomain>
   <MachinePassword>ComputerPassword</MachinePassword>
   <UnsecureJoin>true</UnsecureJoin>
</Identification>
```

## Related topics


[Identification](microsoft-windows-unattendedjoin-identification.md)

 

 







