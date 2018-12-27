---
title: Password
description: Password specifies the password for a LocalAccount to be created during installation and whether the password is hidden in the unattended installation answer file.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7AB3A2BB-DD06-4146-A824-AC34D3BA9D26
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Password

`Password` specifies the password for a [LocalAccount](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount.md) to be created during installation and whether the password is hidden in the unattended installation answer file.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [PlainText](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount-password-plaintext.md) | Specifies whether the [LocalAccount](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount.md) password is hidden in the answer file. |
| [Value](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount-password-value.md) | Specifies the [LocalAccount](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount.md) password. |

## Valid Configuration Passes

offlineServicing

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)| [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md) | [OfflineLocalAccounts](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts.md) | [LocalAccount](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount.md) | **Password**

## Applies To

Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).
