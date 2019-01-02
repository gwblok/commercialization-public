---
title: Password
description: Password
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8475b6c1-7297-43d3-a900-bc560c4165e1
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Password

`Password` specifies the password for the [Username](microsoft-windows-shell-setup-autologon-username.md) account used for autologon to the [Domain](microsoft-windows-shell-setup-autologon-domain.md), and whether the password is made more security-enhanced in the unattended installation answer file.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [PlainText](microsoft-windows-shell-setup-autologon-password-plaintext.md) | Specifies whether the autologon password [Value](microsoft-windows-shell-setup-autologon-password-value.md) is hidden in the answer file. |
| [Value](microsoft-windows-shell-setup-autologon-password-value.md) | Specifies the autologon password. |

## Valid Configuration Passes

auditSystem

oobeSystem

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [AutoLogon](microsoft-windows-shell-setup-autologon.md) | **Password**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md). This setting is not configured in a Nano Server image.

## XML Example

The following XML output shows how to set autologon.

```XML
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
