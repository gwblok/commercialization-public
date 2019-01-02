---
title: PlainText
description: PlainText specifies whether the LocalAccount/Password/Value is hidden in the unattended installation answer file.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 637B85D4-569C-4BA0-A78E-22A3B0755D3E
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PlainText


`PlainText` specifies whether the LocalAccount/Password/[Value](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount-password-value.md) is hidden in the unattended installation answer file.

**Note**  
You can use this setting only to hide the passwords for local accounts . Domain account passwords are not hidden.

 

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
<td><p>Specifies that the password appears in plain text in the answer file. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the password is hidden in the answer file.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
This element appears above the **Settings** bar in the **Properties** pane of Windows System Manager. It always appears as **true** in the user interface (UI), even if you have selected **Hide sensitive data**.

 

## Valid Configuration Passes


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)| [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md) | [OfflineLocalAccounts](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts.md) | [LocalAccount](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount.md) | [Password](microsoft-windows-shell-setup-offlineuseraccounts-offlinelocalaccounts-localaccount-password.md) | **PlainText**

## Applies To


Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

 

 






