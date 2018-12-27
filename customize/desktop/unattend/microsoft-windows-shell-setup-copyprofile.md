---
title: CopyProfile
description: CopyProfile
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6755fa5f-f0cd-4ae4-93b9-62aae78e93fa
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# CopyProfile


`CopyProfile` enables you to customize a user profile and use the customized profile as the default user profile. Windows uses the default user profile as a template to assign a profile to each new user.

**CopyProfile** runs during the specialize configuration pass and should be used after you make customizations to the built-in administrator profile. Using the `CopyProfile` setting often requires a separate answer file to use when run you generalize a computer by running **sysprep**.

Be aware of the following considerations before using `CopyProfile`:

-   On the reference computer, only use the built-in administrator account. Creating multiple accounts might result in copying the wrong user profile as the default profile.

-   Do not use a domain account. The `CopyProfile` setting runs after the computer is removed from the domain during sysprep and settings configured in a domain account will be lost. If you make changes to the default user profile, and then join the computer to a domain, the customizations you made to the default user profile will appear on new domain accounts.

-   Some customizations to the default user profile are not copied, such as items pinned to the task bar. Some settings are reset by the new user logon process. To configure those settings, use Group Policy settings or create scripts to define these user settings.

For more information about using `CopyProfile`, see [Customize the Default User Profile](http://go.microsoft.com/fwlink/p/?linkid=238122).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Changes the default user profile with customizations made . You must set this value to <strong>true</strong> only if you have made customizations to the logged-on user profile that you need to apply to all new users.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Does not change the default user profile. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **CopyProfile**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output specifies that Sysprep copies the customized user profile settings from the built-in administrator account to the default user profile.

```
<CopyProfile>true</CopyProfile>
```

## Related topics


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)

[How to Boot to Audit Mode or OOBE](http://go.microsoft.com/fwlink/p/?linkid=231389)

[Sysprep Technical Reference](http://go.microsoft.com/fwlink/?LinkId=214573)

 

 







