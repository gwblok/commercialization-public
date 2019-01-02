---
title: AdministratorPassword
description: AdministratorPassword
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 429ba2af-d8de-4f8c-89f8-9983953d05c2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# AdministratorPassword

`AdministratorPassword` specifies the administrator password and whether it is hidden in the unattended installation answer file.

To configure a blank administrator password for Windows 7, write an empty string in Windows System Image Manager (Windows SIM), by right-clicking the [Value](microsoft-windows-shell-setup-useraccounts-administratorpassword-value.md) setting, and then selecting **Write Empty String**.

> [!Warning]
> Creating a blank administrator password is a security risk.

By default, the built-in administrator account is disabled in all default clean installations.

You can enable the built-in administrator account during unattended installations, by setting the AutoLogon/[Username](microsoft-windows-shell-setup-autologon-username.md) to **Administrator**. This enables the built-in administrator account, even if a password is not specified in the `AdministratorPassword` setting.

If no values are set for the administrator password and [Username](microsoft-windows-shell-setup-autologon-username.md) is not set to **Administrator**, the administrator account is disabled.

Both **Microsoft-Windows-Shell-Setup | Autologon** and **Microsoft-Windows-Shell-Setup | UserAccounts | AdministratorPassword** sections are now needed for autologon in audit mode to work. Both of these settings should be added to the **auditSystem** configuration pass.

> [!Note]
> For Windows Server 2008, if you run the **sysprep** command with the **generalize** option, the built-in administrator account can no longer access any Encrypting File System (EFS)-encrypted files, personal certificates, and stored passwords for websites or network resources.

## Password Requirements for User Accounts in Windows Server 2008

The built-in Administrator must have a password and that password must be changed at first logon. This will prevent the built-in Administrator account from having a blank password by default.

The default password policy requires the creation of a complex password for all user accounts. During installation of Windows Server 2008, Setup prompts you to configure a complex password. Attempting to configure a non-complex password, either manually or by using a script, such as the **net** command, will fail.

Sysprep sets a blank password for the built-in administrator account during the **sysprep /generalize** process. The next time the computer starts, you, or the end user, are prompted for a password. You can automate configuration of the password by creating an answer file to use with Sysprep that specifies a value for the **Microsoft-Windows-Shell-Setup | UserAccounts | AdministratorPassword** unattended Setup setting.

OEMs and system builders are required to retain the default password policy of their Windows Server 2008 computers. However, corporate customers are permitted to change the default password policy.

A corporate customer can configure a non-complex password for the built-in administrator account during an unattended installation by specifying the desired value for **Microsoft-Windows-Shell-Setup | UserAccounts | AdministratorPassword**.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [PlainText](microsoft-windows-shell-setup-useraccounts-administratorpassword-plaintext.md) | Specifies whether the <code>AdministratorPassword</code> is hidden in the unattended installation answer file. |
| [Value](microsoft-windows-shell-setup-useraccounts-administratorpassword-value.md) | Specifies the <code>AdministratorPassword</code>. |

## Valid Configuration Passes

auditSystem

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [UserAccounts](microsoft-windows-shell-setup-useraccounts.md) | **AdministratorPassword**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output shows how to set [UserAccounts](microsoft-windows-shell-setup-useraccounts.md).

```XML
<UserAccounts>
   <AdministratorPassword>
      <Value>cAB3AEEAZABtAGkAbgBpAHMAdAByAGEAdABvAHIAUABhAHMAcwB3AG8AcgBkAA==</Value>
      <PlainText>false</PlainText>
   </AdministratorPassword>
</UserAccounts>
```

## Related topics

[UserAccounts](microsoft-windows-shell-setup-useraccounts.md)
