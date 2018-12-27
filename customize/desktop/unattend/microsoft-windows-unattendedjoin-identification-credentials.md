---
title: Credentials
description: Credentials
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b2a48f43-e841-4b17-ae68-17da016c30b6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Credentials

`Credentials` specifies the domain, the user name, and the password used to join a domain during Windows Setup.

> [!Note]
> Use either [Provisioning](microsoft-windows-unattendedjoin-identification-provisioning.md) or Credentials to join an account to the domain. The settings in Provisioning will be used to join the account to the domain, if values are entered for both the Provisioning and Credentials settings.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Domain](microsoft-windows-unattendedjoin-identification-credentials-domain.md) | Specifies the domain of the account used when joining a domain. |
| [Password](microsoft-windows-unattendedjoin-identification-credentials-password.md) | Specifies the password of the user account used for authentication when joining a domain. |
| [Username](microsoft-windows-unattendedjoin-identification-credentials-username.md) | Specifies the user account used for authentication when joining a domain. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | **Credentials**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

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

[Identification](microsoft-windows-unattendedjoin-identification.md)
