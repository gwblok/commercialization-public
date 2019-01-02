---
title: Link0
description: Link0
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: fcc8e564-9572-40d4-b491-38cf4a429d59
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Link0


`Link0` specifies the path to the first available program shortcut on the taskbar.

**Note**  
Any item that is pinned to the taskbar will not appear in the **Start** menu list of most frequently used programs.

 

We recommend that you add shortcut files to the All Users **Start** menu, for example: `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Fabrikam\Application.lnk`.

We do not recommend adding the shortcut by using the environment variable: `%USERPROFILE%`. Shortcuts added by using `%USERPROFILE%` are applied only to the profile of the next user to log on to the computer. Also, if the setting is applied during the **auditUser** configuration pass, the shortcut is applied only to the temporary administrator account, which is removed after exiting audit mode.

This setting has no effect on Server Core installations.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path_to_first_link</em></p></td>
<td><p>Specifies the path to the first shortcut on the taskbar. <em>Path_to_first_link</em> is a string with a maximum length of 259 characters.</p>
<p><em></em>Path_to_first_link specifies the complete path and the file name of a shortcut file with an .lnk file name extension. The path to the shortcut file must refer to a location on the destination computer.</p>
<p>The shortcut file must include the complete path and file name of a corresponding program file with an .exe file name extension. The path to the program file must refer to a location on the destination computer.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


auditUser

oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [TaskbarLinks](microsoft-windows-shell-setup-taskbarlinks.md) | **Link0**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to add shortcuts for Remote Desktop Connection, Sound Recorder in the desktop, and the calculator in the desktop.

```
<TaskbarLinks>
   <Link0>%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Accessories\Remote Desktop Connection.lnk</Link0>
   <Link1>%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Accessories\Sound Recorder.lnk</Link1>
   <Link2>%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Accessories\Calculator.lnk</Link2>
</TaskbarLinks>
```

## Related topics


[TaskbarLinks](microsoft-windows-shell-setup-taskbarlinks.md)

 

 







