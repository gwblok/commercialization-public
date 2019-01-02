---
title: OfflineAdministratorPassword
description: OfflineAdministratorPassword
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ACD2964A-069A-4E83-A3B9-08E40176979B
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# OfflineAdministratorPassword

`OfflineAdministratorPassword` specifies the administrator password and whether it is hidden in the unattended installation answer file.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [PlainText](microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword-plaintext.md) | Specifies whether the <code>OfflineAdministratorPassword</code> is hidden in the unattended installation answer file. |
| [Value](microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword-value.md) | Specifies the <code>OfflineAdministratorPassword</code>. |

## Valid Configuration Passes

offlineServicing

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md) | **OfflineAdministratorPassword**

## Applies To

Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to set [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md).

```XML
<OfflineUserAccounts>
   <OfflineAdministratorPassword>
      <Value>cAB3AEEAZABtAGkAbgBpAHMAdAByAGEAdABvAHIAUABhAHMAcwB3AG8AcgBkAA==</Value>
      <PlainText>false</PlainText>
   </OfflineAdministratorPassword>
</OfflineUserAccounts>
```
