---
title: Value
description: Value
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b1bc2250-e860-42ba-a2da-7cbfc5db7cc4
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Value


`Value` specifies the [AdministratorPassword](microsoft-windows-shell-setup-useraccounts-administratorpassword.md). If the computer is connected to a domain, this value must meet domain password complexity requirements.

To configure a blank administrator password, write an empty string in Windows System Image Manager (Windows SIM) by right-clicking on the `Value` setting, and choose **Write Empty String**. The built-in administrator account will be enabled with a blank password.

**Caution**  
Creating a blank administrator password is a security risk.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Password</em></p></td>
<td><p>Specifies the <a href="microsoft-windows-shell-setup-useraccounts-administratorpassword.md" data-raw-source="[AdministratorPassword](microsoft-windows-shell-setup-useraccounts-administratorpassword.md)">AdministratorPassword</a>. <em>Password</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


auditSystem

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [UserAccounts](microsoft-windows-shell-setup-useraccounts.md)| [AdministratorPassword](microsoft-windows-shell-setup-useraccounts-administratorpassword.md) | **Value**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to set [UserAccounts](microsoft-windows-shell-setup-useraccounts.md).

```
<UserAccounts>
   <AdministratorPassword>
      <Value>cAB3AEEAZABtAGkAbgBpAHMAdAByAGEAdABvAHIAUABhAHMAcwB3AG8AcgBkAA==</Value>
      <PlainText>false</PlainText>
   </AdministratorPassword>
</UserAccounts>
```

## Related topics


[AdministratorPassword](microsoft-windows-shell-setup-useraccounts-administratorpassword.md)

 

 







