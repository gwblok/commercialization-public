---
title: Value
description: Value specifies the OfflineAdministratorPassword. If the computer is connected to a domain, this value must meet domain password complexity requirements.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: F1FC75C2-5A65-4F8F-A406-2B40C8F8830A
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Value


`Value` specifies the [OfflineAdministratorPassword](microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword.md). If the computer is connected to a domain, this value must meet domain password complexity requirements.

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
<td><p>Specifies the <a href="microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword.md" data-raw-source="[OfflineAdministratorPassword](microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword.md)">OfflineAdministratorPassword</a>. <em>Password</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md) | [OfflineAdministratorPassword](microsoft-windows-shell-setup-offlineuseraccounts-offlineadministratorpassword.md) | **Value**

## Applies To


Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

 

 






