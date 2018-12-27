---
title: Group
description: Group
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a85e433e-13aa-41f3-a4e8-6c07e87f6d9f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Group


`Group` specifies the name of an existing local security group to which a new [LocalAccount](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount.md) will be added during installation. You can add a user to multiple groups by entering multiple group names separated by semicolons.

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
<td><p>Specifies the existing local security group for the local account. More than one group can be specified (separated by semicolons). <em>Group_name</em> is a string with a maximum length of 256 characters.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


auditSystem

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [UserAccounts](microsoft-windows-shell-setup-useraccounts.md) | [LocalAccounts](microsoft-windows-shell-setup-useraccounts-localaccounts.md) | [LocalAccount](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount.md) | **Group**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to set [UserAccounts](microsoft-windows-shell-setup-useraccounts.md).

```
<UserAccounts>
   <LocalAccounts>
      <LocalAccount wcm:action="add">
         <Password>
            <Value>cAB3AFAAYQBzAHMAdwBvAHIAZAA</Value>
            <PlainText>false</PlainText>
         </Password>
         <Description>Test account</Description>
         <DisplayName>Admin/Power User Account</DisplayName>
         <Group>Administrators;Power Users</Group>
         <Name>Test1</Name>
      </LocalAccount>
      <LocalAccount wcm:action="add">
         <Password>
            <Value>cABhAHMAcwB3AG8AcgBkAFAAYQBzAHMAdwBvAHIAZAA=</Value>
            <PlainText>false</PlainText>
         </Password>
         <Description>For testing</Description>
         <DisplayName>Admin Account</DisplayName>
         <Group>Administrators</Group>
         <Name>Test2</Name>
      </LocalAccount>
   </LocalAccounts>
</UserAccounts>
```

## Related topics


[LocalAccount](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount.md)

 

 







