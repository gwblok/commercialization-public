---
title: Group
description: Group
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: B0DCC2E9-CFD3-4F51-8991-90A6BFCF44B3
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

-   Guests

-   PowerUsers

-   PrintOperators

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


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md) | [OfflineDomainAccounts](microsoft-windows-shell-setup-offlineuseraccounts-offlinedomainaccounts.md) | [OfflineDomainAccount](microsoft-windows-shell-setup-offlineuseraccounts-offlinedomainaccounts-offlinedomainaccount.md) | **Group**

## Applies To


Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML examples show how to use the **Group** setting to add domain groups to local security groups.

Example 1:

```
   <OfflineDomainAccounts>
      <OfflineDomainAccount wcm:action="add">
        <Group>Users</Group> 
        <Name>Domain Users</Name> 
      </OfflineDomainAccount>
   </OfflineDomainAccounts>
```

Example 2:

```
   <OfflineDomainAccounts>
      <OfflineDomainAccount wcm:action="add">
        <Group>Administrators</Group> 
        <Name>Domain Administrators</Name> 
      </OfflineDomainAccount>
   </OfflineDomainAccounts>
```

 

 






