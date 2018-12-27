---
title: Value
description: Value
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ed9ca238-2fe8-4c22-a22e-16f3b275c3f8
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Value


`Value` specifies the [Password](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount-password.md) for a [LocalAccount](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount.md) created during installation.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Password</em></p></td>
<td><p>Specifies the <a href="microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount-password.md" data-raw-source="[Password](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount-password.md)">Password</a> for a <a href="microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount.md" data-raw-source="[LocalAccount](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount.md)">LocalAccount</a>. <em>Password</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


auditSystem

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [UserAccounts](microsoft-windows-shell-setup-useraccounts.md) | [LocalAccounts](microsoft-windows-shell-setup-useraccounts-localaccounts.md) | [LocalAccount](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount.md) | [Password](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount-password.md) | **Value**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

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


[Password](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount-password.md)

 

 







