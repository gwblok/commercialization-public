---
title: Value
description: Value
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f249d028-8a59-49e6-8de6-8569adf56c3b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Value


`Value` specifies the autologon [Password](microsoft-windows-shell-setup-autologon-password.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Password</em></p></td>
<td><p>Specifies the autologon password. <em>Password</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


auditSystem

oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [AutoLogon](microsoft-windows-shell-setup-autologon.md) | [Password](microsoft-windows-shell-setup-autologon-password.md) | **Value**

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


[Password](microsoft-windows-shell-setup-autologon-password.md)

 

 







