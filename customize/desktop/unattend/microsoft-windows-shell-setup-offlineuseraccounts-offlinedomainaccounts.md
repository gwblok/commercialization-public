---
title: OfflineDomainAccounts
description: OfflineDomainAccounts specifies the details of domain accounts to be added to local security groups on the computer during installation.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 505C1B2B-1F8A-4C5B-8944-CD9BC44DF36D
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# OfflineDomainAccounts

`OfflineDomainAccounts` specifies the details of domain accounts to be added to local security groups on the computer during installation.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [OfflineDomainAccount](microsoft-windows-shell-setup-offlineuseraccounts-offlinedomainaccounts-offlinedomainaccount.md) | Specifies the domains and the domain accounts to be created. |

## Valid Configuration Passes

offlineServicing

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md) | **OfflineDomainAccounts**

## Applies To

Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).
