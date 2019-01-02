---
title: Identification
description: Identification
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8de86456-1cd7-4c63-a03d-b03191be8874
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Identification

`Identification` specifies credentials to join a domain, the name of the domain to join, the workgroup to assign to the computer, and other options.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
|[Credentials](microsoft-windows-unattendedjoin-identification-credentials.md)|Specifies [Domain](microsoft-windows-unattendedjoin-identification-credentials-domain.md), [Username](microsoft-windows-unattendedjoin-identification-credentials-username.md), and [Password](microsoft-windows-unattendedjoin-identification-credentials-password.md) used to join a domain for an unattended installation.|
|[DebugJoin](microsoft-windows-unattendedjoin-identification-debugjoin.md)|Specifies whether to run a debug routine after any unattended domain-join attempts have failed. The routine breaks into the kernel debugger.|
|[DebugJoinOnlyOnThisError](microsoft-windows-unattendedjoin-identification-debugjoinonlyonthiserror.md)|Specifies a debugging routine to start in [DebugJoin](microsoft-windows-unattendedjoin-identification-debugjoin.md) only after encountering an error specified in the setting.|
|[JoinDomain](microsoft-windows-unattendedjoin-identification-joindomain.md)|Specifies the name of the domain to join. If this value is set, [JoinWorkgroup](microsoft-windows-unattendedjoin-identification-joinworkgroup.md) is ignored.|
|[JoinWorkgroup](microsoft-windows-unattendedjoin-identification-joinworkgroup.md)|Specifies the name of the workgroup to assign to a computer. If this value is set, [JoinDomain](microsoft-windows-unattendedjoin-identification-joindomain.md) cannot be set.|
|[MachineObjectOU](microsoft-windows-unattendedjoin-identification-machineobjectou.md)|Specifies the Lightweight Directory Access Protocol (LDAP) X.500-distinguished name of the organizational unit (OU) in which the computer account is created. This account is in Active Directory on a domain controller in the domain to which the computer is being joined.|
|[MachinePassword](microsoft-windows-unattendedjoin-identification-machinepassword.md)|Specifies the unique password for the computer. Typically, this setting is not required unless the computer account has been previously created in the domain.|
|[Provisioning](microsoft-windows-unattendedjoin-identification-provisioning.md)|Specifies the account information used to join a domain during Windows Setup.|
|[TimeoutPeriodInMinutes](microsoft-windows-unattendedjoin-identification-timeoutperiodinminutes.md)|Specifies the number of minutes that Windows will wait before timing out when Windows tries to join a domain. This change increases the default timeout from 7 to 15 minutes.|
|[UnsecureJoin](microsoft-windows-unattendedjoin-identification-unsecurejoin.md)|Specifies adding the computer to the domain without requiring a unique password.|

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | **Identification**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example

The following XML output shows how to set the identification settings.

```XML
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

[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md)
