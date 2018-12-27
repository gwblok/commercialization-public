---
title: Link4
description: Link4
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 65711c58-e13b-4677-a8ae-6bda793adc71
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Link4


`Link4` specifies the path to the first available program shortcut on the taskbar.

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


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [TaskbarLinks](microsoft-windows-shell-setup-taskbarlinks.md) | **Link4**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to add shortcuts for Remote Desktop Connection, Sound Recorder in the desktop, calculator in the desktop, Snipping Tool, Sticky Notes, and Wordpad on the taskbar.

```
<TaskbarLinks>
   <Link0>%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Accessories\Remote Desktop Connection.lnk</Link0>
   <Link1>%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Accessories\Sound Recorder.lnk</Link1>
   <Link2>%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Accessories\Calculator.lnk</Link2>
   <Link3>%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Accessories\Snipping Tool.lnk</Link3>
   <Link4>%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Accessories\Sticky Notes.lnk</Link4>
   <Link5>%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Accessories\Wordpad.lnk</Link5>
</TaskbarLinks>
```

## Related topics


[TaskbarLinks](microsoft-windows-shell-setup-taskbarlinks.md)

 

 







