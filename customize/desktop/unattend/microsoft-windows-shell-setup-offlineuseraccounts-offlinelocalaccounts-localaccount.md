---
title: LocalAccount
description: LocalAccount specifies the details of a local account to be created during installation.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 149399A6-1293-4A71-9422-954D259F42A8
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# LocalAccount

`LocalAccount` specifies the details of a local account to be created during installation.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Description](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount-description.md) | Specifies a <code>LocalAccount</code>. |
| [DisplayName](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount-displayname.md) | Specifies the display name for a <code>LocalAccount</code>. |
| [Group](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount-group.md) | Specifies the name of existing local security groups to which a <code>LocalAccount</code> will be added. |
| [Name](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount-name.md) | Specifies the user name for a <code>LocalAccount</code>. |
| [Password](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount-password.md) | Specifies the password for a <code>LocalAccount</code> and whether the password is hidden in the unattended installation answer file. |

## Valid Configuration Passes

offlineServicing

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)| [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md) | [OfflineLocalAccounts](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts.md) | **LocalAccount**

## Applies To

Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).
