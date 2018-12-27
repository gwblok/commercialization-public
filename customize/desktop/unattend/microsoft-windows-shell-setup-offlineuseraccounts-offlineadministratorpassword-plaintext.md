---
title: PlainText
description: PlainText specifies whether the OfflineAdministratorPassword is hidden in the unattended installation answer file.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 15DA23F0-0C66-4295-B08B-DB749CB02CF8
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PlainText


`PlainText` specifies whether the [OfflineAdministratorPassword](microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword.md) is hidden in the unattended installation answer file.

**Note**  
You can only use this setting to hide the passwords for offline user accounts only. Domain account passwords are not hidden.

 

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
<td><p>Specifies that the <a href="microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword.md" data-raw-source="[OfflineAdministratorPassword](microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword.md)">OfflineAdministratorPassword</a> appears in plain text in the answer file. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the <a href="microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword.md" data-raw-source="[OfflineAdministratorPassword](microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword.md)">OfflineAdministratorPassword</a> is hidden in the answer file.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
This element appears above the **Settings** bar in the **Properties** pane of Windows System Manager. It always appears as **true** in the user interface (UI), even if you have selected **Hide sensitive data**.

 

## Valid Configuration Passes


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md) | [OfflineAdministratorPassword](microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword.md) | **PlainText**

## Applies To


Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to set the password for [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md).

```
<OfflineUserAccounts>
   <OfflineAdministratorPassword>
      <Value>cAB3AEEAZABtAGkAbgBpAHMAdAByAGEAdABvAHIAUABhAHMAcwB3AG8AcgBkAA==</Value>
      <PlainText>false</PlainText>
   </OfflineAdministratorPassword>
</OfflineUserAccounts>
```

 

 






