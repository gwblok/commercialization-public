---
title: OfflineDomainAccount
description: OfflineDomainAccount specifies the details of a domain account to be added to local security groups on the computer.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2D5C2EA6-8B98-47C4-8338-A8109316936B
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# OfflineDomainAccount

`OfflineDomainAccount` specifies the details of a domain account to be added to local security groups on the computer.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Group](microsoft-windows-shell-setup-offlineuseraccounts-offlinedomainaccounts-offlinedomainaccount-group.md) | Specifies the group to which the domain account belongs. |
| [SID](microsoft-windows-shell-setup-offlineuseraccounts-offlinedomainaccounts-offlinedomainaccount-sid.md) | Specifies the security identifier of the domain account. |

## Valid Configuration Passes

offlineServicing

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md) | [OfflineDomainAccounts](microsoft-windows-shell-setup-offlineuseraccounts-offlinedomainaccounts.md) | **OfflineDomainAccount**

## Applies To

Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).
