---
title: OfflineIdentification
description: OfflineIdentification
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1D630A37-BC16-4CD6-98CA-7DECE0BEE85E
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# OfflineIdentification

`OfflineIdentification` specifies the account information used to join a domain during Windows Setup.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Provisioning](microsoft-windows-unattendedjoin-offlineidentification-provisioning.md) | Specifies the account information used to join a domain during Windows Setup. |

## Valid Configuration Passes

offlineServicing

## Parent Hierarchy

[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | **OfflineIdentification**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example

The following XML output shows how to set the identification settings.

```XML
<OfflineIdentification>
  <Provisioning>
    <AccountData>BASE64-ENCODED-BLOB</AccountData>
  </Provisioning>
</OfflineIdentification>
```

## Related topics

[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md)
