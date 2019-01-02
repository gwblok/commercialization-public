---
title: Provisioning
description: Provisioning
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9d12928f-0e12-4925-a8b0-2c07bc0de3af
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Provisioning

`Provisioning` specifies the account information used to join a domain during Windows Setup.

> [!Note]
> Use either Provisioning or [Credentials](microsoft-windows-unattendedjoin-identification-credentials.md) to join an account to the domain. The settings in Provisioning will be used to join the account to the domain, if values are entered for both the Provisioning and Credentials settings.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AccountData](microsoft-windows-unattendedjoin-identification-provisioning-accountdata.md) | Specifies account data used when joining a domain. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | **Provisioning**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example

The following XML output shows how to set the Provisioning settings.

```XML
<Identification>
<Provisioning>
<AccountData>BASE64-ENCODED-BLOB</AccountData>
</Provisioning>
</Identification>
```

## Related topics

[Identification](microsoft-windows-unattendedjoin-identification.md)
