---
title: OfflineLocalAccounts
description: OfflineLocalAccounts specifies offline local accounts to be created during installation.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 72A51941-7077-4646-BB6C-3CE075C36824
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# OfflineLocalAccounts

`OfflineLocalAccounts` specifies offline local accounts to be created during installation.

You can use the **sysprep/generalize** command in conjunction with `OfflineLocalAccounts` to change account information. See the [Best Practices for Authoring Answer Files](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/best-practices-for-authoring-answer-files) topic for details.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [LocalAccount](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount.md) | Specifies a local account to be created during installation. |

## Valid Configuration Passes

offlineServicing

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)| [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md) | **OfflineLocalAccounts**

## Applies To

Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).
