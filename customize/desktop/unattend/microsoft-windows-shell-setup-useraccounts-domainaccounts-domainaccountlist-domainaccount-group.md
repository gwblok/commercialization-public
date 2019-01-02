---
title: Group
description: Group
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 08f9c3ed-d6e1-4950-aa4c-fcf04680c387
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Group


`Group` specifies the local security group to which the domain account or the security group will be added. You can add a user to multiple groups by entering multiple group names separated by semicolons.

The [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) component recognizes the following English group names and sets the appropriate localized group name, regardless of the default language of the Windows image:

-   AccountOperators

-   Administrators

-   BackupOperators

-   CryptoOperators

-   DCOMUsers

-   Guests

-   IUsers

-   NetworkConfigurationOperators

-   PerfLoggingUsers

-   PerfMonitoringUsers

-   PowerUsers

-   PrintOperators

-   RemoteDesktopUsers

-   Replicator

-   SystemOperators

-   Users

Specify the account names and group names by using language-neutral names. The language-neutral account and group names are specified in English—for example, **Administrators**, **Power Users**, and **Guest**. This is required because the shell account settings are processed before a default user interface (UI) language is applied to the computer.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Group_name</em></p></td>
<td><p>Specifies the local security group to which the domain account or the security group will be added. More than one group can be specified (separated by semicolons). <em>Group_name</em> is a string with a maximum length of 256 characters.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


auditSystem

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [UserAccounts](microsoft-windows-shell-setup-useraccounts.md) | [DomainAccounts](microsoft-windows-shell-setup-useraccounts-domainaccounts.md) | [DomainAccountList](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist.md) | [DomainAccount](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist-domainaccount.md) | **Group**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML examples show how to use the **Group** setting to add domain groups to local security groups.

Example 1:

```
<DomainAccounts>
   <DomainAccountList wcm:action="add">
      <DomainAccount wcm:action="add">
        <Group>Users</Group> 
        <Name>Domain Users</Name> 
      </DomainAccount>
   <Domain>FabrikamDomain</Domain> 
   </DomainAccountList>
</DomainAccounts>
```

Example 2:

```
<DomainAccounts>
   <DomainAccountList wcm:action="add">
      <DomainAccount wcm:action="add">
        <Group>Administrators</Group> 
        <Name>Domain Administrators</Name> 
      </DomainAccount>
   <Domain>FabrikamDomain</Domain> 
   </DomainAccountList>
</DomainAccounts>
```

## Related topics


[DomainAccount](microsoft-windows-shell-setup-useraccounts-domainaccounts-domainaccountlist-domainaccount.md)

 

 







