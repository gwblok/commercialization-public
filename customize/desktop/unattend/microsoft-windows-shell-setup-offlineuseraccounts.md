---
title: OfflineUserAccounts
description: OfflineUserAccounts specifies local accounts to be created, domain accounts to be added, and the administrator password.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: A27B836F-2584-4166-ACCD-618D8211BC14
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# OfflineUserAccounts

`OfflineUserAccounts` specifies local accounts to be created, domain accounts to be added, and the administrator password.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [OfflineAdministratorPassword](microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword.md) | Specifies the administrator password for the computer and whether it is hidden in the unattended installation answer file. |
| [OfflineDomainAccounts](microsoft-windows-shell-setup-offlineuseraccounts-offlinedomainaccounts.md) | Specifies the details of domain accounts to be added to local security groups on the computer during installation. |
| [OfflineLocalAccounts](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts.md) | Specifies the details of local accounts to be created during installation. |

## Valid Configuration Passes

offlineServicing

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **OfflineUserAccounts**

## Applies To

Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to set `OfflineUserAccounts`.

```XML
<OfflineUserAccounts>
     <OfflineAdministratorPassword>
        <Value>[PasswordValue]</Value>
        <PlainText>[true/false]</PlainText>
     </OfflineAdministratorPassword>

     <OfflineLocalAccounts>
         <LocalAccount>
             <Password>
                 <Value>[PasswordValue]</Value>
                 <PlainText>[true/false]</PlainText>
             </Password>
             <Group>[groups]</Group>
             <Name>[user]</Name>
             <DisplayName>[userdisplayname]</DisplayName>
         </LocalAccount>
     </OfflineLocalAccounts>

     <OfflineDomainAccounts>
         <OfflineDomainAccount>
             <SID>[SID1]</SID>
             <Group>[groups]</Group>
         </OfflineDomainAccount>
         <OfflineDomainAccount>
             <SID>[SID2]</SID>
             <Group>[groups]</Group>
         </OfflineDomainAccount>
    </OfflineDomainAccounts>
</OfflineUserAccounts>
```

## Related topics

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)
