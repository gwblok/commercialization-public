---
title: LocalAccounts
description: LocalAccounts
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 901c66a1-d0a0-4e6e-8033-ff296c3e52e8
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# LocalAccounts

`LocalAccounts` specifies local accounts to be created during installation.

You can use the **sysprep/generalize** command in conjunction with `LocalAccounts` to change account information. See the [Best Practices for Authoring Answer Files](http://go.microsoft.com/fwlink/?LinkId=268345) topic for details.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [LocalAccount](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount.md) | Specifies a local account to be created during installation. |

## Valid Configuration Passes

auditSystem

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)| [UserAccounts](microsoft-windows-shell-setup-useraccounts.md) | **LocalAccounts**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to set user accounts.

```XML
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

[UserAccounts](microsoft-windows-shell-setup-useraccounts.md)
