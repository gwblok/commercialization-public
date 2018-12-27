---
title: Username
description: Username
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b3388d91-580e-40c1-b0ef-d4729b47074b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Username


`Username` specifies a local account or a domain user account on the domain specified by the [Domain](microsoft-windows-shell-setup-autologon-domain.md).

By default, the built-in administrator account is disabled in all default clean installations. You can enable the built-in Administrator account during unattended installations, by setting `Username` to **Administrator** (only the English word will automatically enable the account). This enables the built-in administrator account, even if a password is not specified in [AdministratorPassword](microsoft-windows-shell-setup-useraccounts-administratorpassword.md).

If you are deploying a multilingual Windows image, you should specify account names and group names, by using the language-neutral names. The language-neutral account and group names are specified in English, for example, **Administrators**, **Power Users**, and **Guest**. This is required because the shell account settings are processed before a default user interface (UI) language is applied to the computer.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Username</em></p></td>
<td><p>Specifies the user account name used for autologon. <em>Username</em> is a string with a maximum length of 256 characters.</p>
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

specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [AutoLogon](microsoft-windows-shell-setup-autologon.md) | **Username**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md). This setting is not configured in a Nano Server image.

## XML Example


The following XML output shows how to set autologon.

```
<AutoLogon>
   <Password>
      <Value>MyPassword</Value> 
      <PlainText>true</PlainText>
   </Password>
   <Domain>FabrikamDomain</Domain>
   <Enabled>true</Enabled> 
   <LogonCount>2</LogonCount> 
   <Username>MyUserName</Username> 
</AutoLogon>
```

## Related topics


[AutoLogon](microsoft-windows-shell-setup-autologon.md)

 

 







