---
title: Link1
description: Link1
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8bf3b207-e726-4320-98cf-0f891f13b079
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Link1


`Link1` specifies the path to the second available program shortcut on the taskbar.

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
<td><p><em>Path_to_second_link</em></p></td>
<td><p>Specifies the path to the second program shortcut on the taskbar. <em>Path_to_second_link</em> is a string with a maximum length of 259 characters.</p>
<p><em>Path_to_second_link</em> specifies the complete path and the file name of a shortcut file with a .lnk file name extension. The path to the shortcut file must refer to a location on the destination computer.</p>
<p>The shortcut file must include the complete path and file name of a corresponding program file with a .exe file name extension. The path to the program file must refer to a location on the destination computer.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


auditUser

oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [TaskbarLinks](microsoft-windows-shell-setup-taskbarlinks.md) | **Link1**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

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

 

 







