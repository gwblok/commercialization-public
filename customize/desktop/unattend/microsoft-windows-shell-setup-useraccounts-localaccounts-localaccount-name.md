---
title: Name
description: Name
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5173b942-b170-40ac-9fe8-ac520f2d242e
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Name


`Name` specifies the user name for a [LocalAccount](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount.md) to be created during installation.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Name</em></p></td>
<td><p>Specifies the name of a <a href="microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount.md" data-raw-source="[LocalAccount](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount.md)">LocalAccount</a>. <em>Name</em> is a string with a maximum length of 256 characters.</p>
<p>Do not use any of the following characters: &amp;amp;quot;/[]:|&amp;amp;lt;&amp;amp;gt;+=;,?*%@</p>
<p>Do not use the name &quot;NONE&quot;, this is a restricted username.</p>
<p>This string type does not support empty elements. Do not create an empty value for this setting.</p>
<p>Some Unicode characters such as emoji appear as with the placeholder character: ? (question mark) in command prompts, but appear correctly in other locations such as File Explorer.</p>
<p>Users who sign-in with a Microsoft account will frequently see that their underlying profile path does not match their firstname / lastname. When this happens, you will see an account in the form: username_001.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


auditSystem

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [UserAccounts](microsoft-windows-shell-setup-useraccounts.md) | [LocalAccounts](microsoft-windows-shell-setup-useraccounts-localaccounts.md) | [LocalAccount](microsoft-windows-shell-setup-useraccounts-localaccounts-localaccount.md) | **Name**

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

 

 







