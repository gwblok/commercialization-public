---
title: DomainAccounts
description: DomainAccounts
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1b9eec7d-be85-4e61-8df7-63aa5a9b4be1
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# DomainAccounts

`DomainAccounts` specifies the details of domain accounts to be added to local security groups on the computer during installation.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DomainAccountList](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist.md) | Specifies the domains and the domain accounts to be created. |

## Valid Configuration Passes

auditSystem

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [UserAccounts](microsoft-windows-shell-setup-useraccounts.md) | **DomainAccounts**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to set [UserAccounts](microsoft-windows-shell-setup-useraccounts.md).

```XML
<UserAccounts>
   <DomainAccounts>
      <DomainAccountList wcm:action="add">
         <DomainAccount wcm:action="add">
            <Name>account1</Name>
            <Group>Fabrikam\Group1</Group>
         </DomainAccount>
         <DomainAccount wcm:action="add">
            <Name>account2</Name>
            <Group>Fabrikam\Group2</Group>
         </DomainAccount>
         <Domain>domain1</Domain>
      </DomainAccountList>
      <DomainAccountList wcm:action="add">
         <DomainAccount wcm:action="add">
            <Name>account3</Name>
            <Group>Fabrikam\Group2</Group>
         </DomainAccount>
         <Domain>domain2</Domain>
     </DomainAccountList>
   </DomainAccounts>
</UserAccounts>
```

## Related topics

[UserAccounts](microsoft-windows-shell-setup-useraccounts.md)
