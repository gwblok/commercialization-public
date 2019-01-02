---
title: PlainText
description: PlainText
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3ba4cc94-b86a-4c0a-8224-e6f24f542103
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PlainText


`PlainText` specifies whether the [AdministratorPassword](microsoft-windows-shell-setup-useraccounts-administratorpassword.md) is hidden in the unattended installation answer file.

**Note**  
You can only use this setting to hide the passwords for local accounts only. Domain account passwords are not hidden.

 

You cannot set this value directly. Select **Hide sensitive data** on the **Tools** menu to hide all passwords with a `PlainText` setting in your answer file.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the <a href="microsoft-windows-shell-setup-useraccounts-administratorpassword.md" data-raw-source="[AdministratorPassword](microsoft-windows-shell-setup-useraccounts-administratorpassword.md)">AdministratorPassword</a> appears in plain text in the answer file. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the <a href="microsoft-windows-shell-setup-useraccounts-administratorpassword.md" data-raw-source="[AdministratorPassword](microsoft-windows-shell-setup-useraccounts-administratorpassword.md)">AdministratorPassword</a> is hidden in the answer file.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
This element appears above the **Settings** bar in the **Properties** pane of Windows System Manager. It always appears as **true** in the user interface (UI), even if you have selected **Hide sensitive data**.

 

## Valid Configuration Passes


auditSystem

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [UserAccounts](microsoft-windows-shell-setup-useraccounts.md) | [AdministratorPassword](microsoft-windows-shell-setup-useraccounts-administratorpassword.md) | **PlainText**

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

 

 







