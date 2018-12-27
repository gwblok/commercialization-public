---
title: DomainAccount
description: DomainAccount
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2a1579b2-df8f-4116-b56d-a3078e28c856
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# DomainAccount

`DomainAccount` specifies the details of a domain account to be added to local security groups on the computer.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Group](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist-domainaccount-group.md) | Specifies the group to which the <code>DomainAccount</code> belongs. |
| [Name](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist-domainaccount-name.md) | Specifies the name of the <code>DomainAccount</code>. |

## Valid Configuration Passes

auditSystem

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [UserAccounts](microsoft-windows-shell-setup-useraccounts.md) | [DomainAccounts](microsoft-windows-shell-setup-useraccounts-domainaccounts.md) | [DomainAccountList](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist.md) | **DomainAccount**

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

[DomainAccountList](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist.md)
