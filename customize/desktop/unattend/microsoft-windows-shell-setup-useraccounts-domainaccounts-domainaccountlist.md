---
title: DomainAccountList
description: DomainAccountList
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1e4395fa-c516-44d3-9ced-a69f70744c59
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# DomainAccountList

`DomainAccountList` is a list item type that specifies the domains and the domain accounts to be created and added to local security groups on the computer during installation.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Domain](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist-domain.md) | Specifies the name of the domain for the <code>DomainAccountList</code>. |
| [DomainAccount](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist-domainaccount.md) | Specifies the details of domain accounts to be added to local security groups on the computer during installation. |

## Valid Configuration Passes

auditSystem

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [UserAccounts](microsoft-windows-shell-setup-useraccounts.md) | [DomainAccounts](microsoft-windows-shell-setup-useraccounts-domainaccounts.md) | **DomainAccountList**

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
         </DomainAccount wcm:action="add">
         <Domain>domain1</Domain>
      </DomainAccountList>
      <DomainAccountList wcm:action="add">
         <DomainAccount wcm:action="add">
            <Name>account3</Name>
            <Group>Fabrikam\Group2</Group>
         </DomainAccount wcm:action="add">
         <Domain>domain2</Domain>
     </DomainAccountList>
   </DomainAccounts>
</UserAccounts>
```

## Related topics

[DomainAccounts](microsoft-windows-shell-setup-useraccounts-domainaccounts.md)
