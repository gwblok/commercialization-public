---
title: Domain
description: Domain
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 857f3603-789f-4245-a79f-d0e5f9eed91c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Domain


`Domain` specifies the name of the domain for a [DomainAccountList](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path_to_file</em></p></td>
<td><p>Specifies the name of the domain for a <a href="microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist.md" data-raw-source="[DomainAccountList](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist.md)">DomainAccountList</a>. <em>Path_to_file</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


auditSystem

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [UserAccounts](microsoft-windows-shell-setup-useraccounts.md) | [DomainAccounts](microsoft-windows-shell-setup-useraccounts-domainaccounts.md) | [DomainAccountList](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist.md) | **Domain**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to set [UserAccounts](microsoft-windows-shell-setup-useraccounts.md).

```
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

 

 







