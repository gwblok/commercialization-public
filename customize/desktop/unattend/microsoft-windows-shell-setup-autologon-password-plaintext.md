---
title: PlainText
description: PlainText
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 73632592-650e-4eac-a5cb-79227672fca0
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PlainText


`PlainText` specifies whether the AutoLogon/Password/[Value](microsoft-windows-shell-setup-autologon-password-value.md) is hidden in the unattend installation answer file.

**Note**  
You can use this setting only to hide the passwords for local accounts only. Domain account passwords are not hidden.

 

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


auditSystem

oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [AutoLogon](microsoft-windows-shell-setup-autologon.md) | [Password](microsoft-windows-shell-setup-autologon-password.md) | **PlainText**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md). This setting is not configured in a Nano Server image.

## XML Example


The following XML output shows how to set autologon.

```
<AutoLogon>
   <Password>
      <Value>YwBvAG0AcABsAGUAeABfAHAAYQBzAHMAdwBvAHIAZABQAGEAcwBzAHcAbwByAGQA</Value> 
      <PlainText>false</PlainText>
   </Password>
   <Enabled>true</Enabled> 
   <LogonCount>2</LogonCount> 
   <Username>MyUserName</Username> 
   <Domain />
</AutoLogon>
```

## Related topics


[Password](microsoft-windows-shell-setup-autologon-password.md)

 

 







