---
title: Microsoft-Windows-Embedded-KeyboardFilterService
description: Microsoft-Windows-Embedded-KeyboardFilterService
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 40C43C76-AB54-44D4-8547-401F8235B48E


ms.date: 05/02/2017
ms.topic: article


---

# Microsoft-Windows-Embedded-KeyboardFilterService

You can use KeyboardFilterService in to suppress undesirable key presses or key combinations. Normally, a customer can use certain Windows key combinations like Ctrl+Alt+Delete or Ctrl+Shift+Tab to alter the operation of a device by locking the screen or using Task Manager to close a running application. This may not be desirable if your device is intended for a dedicated purpose. However, you can use KeyboardFilterService to suppress any key press or key combination that causes an undesirable system behavior.

>[!Tip]
> For Unattend code samples that show how to suppress various key strokes and shortcuts, see the topics below. For more general information about this feature, see [Customizations for Enterprise - Keyboard Filter](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/keyboardfilter).

## Child elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Alt](Microsoft-Windows-Embedded-KeyboardFilterService-alt.md)|Blocks both Alt keys. |
| [AltF4](Microsoft-Windows-Embedded-KeyboardFilterService-altf4.md) |Blocks the Alt+F4 key combination used to close applications. |
| [AltSpace](Microsoft-Windows-Embedded-KeyboardFilterService-altspace.md) | Blocks the Alt+Space key combination used to open the shortcut menu for the active window. |
| [AltTab](Microsoft-Windows-Embedded-KeyboardFilterService-alttab.md) | Blocks the Alt+Tab key combination used to switch tasks. Also blocks the Alt+Shift+Tab key combination.|
| [AltWin](Microsoft-Windows-Embedded-KeyboardFilterService-altwin.md) | Blocks all keyboard combinations beginning with Alt + Windows logo key, for example Alt + Win + S. |
| [BrowserBack](Microsoft-Windows-Embedded-KeyboardFilterService-browserback.md) | Blocks the Browser Back key. |
| [BrowserFavorites](Microsoft-Windows-Embedded-KeyboardFilterService-browserfavorites.md) | Blocks the Browser Favorites key. |
| [BrowserForward](Microsoft-Windows-Embedded-KeyboardFilterService-browserforward.md)|Blocks the Browser Forward key.|
| [BrowserHome](Microsoft-Windows-Embedded-KeyboardFilterService-browserhome.md)|Blocks the Browser Home key.|
| [BrowserRefresh](Microsoft-Windows-Embedded-KeyboardFilterService-browserrefresh.md)|Blocks the Browser Refresh key.|
| [BrowserSearch](Microsoft-Windows-Embedded-KeyboardFilterService-browsersearch.md)|Blocks the Browser Search key.|
| [BrowserStop](Microsoft-Windows-Embedded-KeyboardFilterService-browserstop.md)|Blocks the Browser Stop key.|
| [ControlAltDelete](Microsoft-Windows-Embedded-KeyboardFilterService-controlaltdelete.md)|Blocks the Control+Alt+Delete key combination used to open the Windows Security screen.|
| [ControlEscape](Microsoft-Windows-Embedded-KeyboardFilterService-controlescape.md)|Blocks the Control+Escape key combination used to open the Start screen.|
| [ControlTab](Microsoft-Windows-Embedded-KeyboardFilterService-controltab.md)|Blocks the Control+Tab key combination used to switch windows.|
| [ControlWindowsF](Microsoft-Windows-Embedded-KeyboardFilterService-controlwindowsf.md)|Blocks the Control+Windows logo key+F key combination used to open the Find Computers dialog box.|
|[Ctrl](Microsoft-Windows-Embedded-KeyboardFilterService-ctrl.md)|Blocks both Ctrl keys.|
|[CtrlF4](Microsoft-Windows-Embedded-KeyboardFilterService-ctrlf4.md)|Blocks the Control+F4 key combination used to close the active window.|
|[CtrlWin](Microsoft-Windows-Embedded-KeyboardFilterService-ctrlwin.md)|Blocks the Ctrl + Windows logo key keyboard combination.|
|[CustomFilters](Microsoft-Windows-Embedded-KeyboardFilterService-customfilters.md)|Blocks the list of custom keys.|
|[CustomScancodes](Microsoft-Windows-Embedded-KeyboardFilterService-customscancodes.md)|Blocks the list of custom scan codes.|
|[DisableKeyboardFilterForAdministrators](Microsoft-Windows-Embedded-KeyboardFilterService-disablekeyboardfilterforadministrators.md)|Disables the keyboard filter for administrators.|
|[Escape](Microsoft-Windows-Embedded-KeyboardFilterService-escape.md)|Blocks the Escape key.|
|[F21](Microsoft-Windows-Embedded-KeyboardFilterService-f21.md)|Blocks the F21 key.|
|[ForceOffAccessibility](Microsoft-Windows-Embedded-KeyboardFilterService-forceoffaccessibility.md)|Disables all Ease of Access features and prevents users from enabling them.|
|[LaunchApp1](Microsoft-Windows-Embedded-KeyboardFilterService-launchapp1.md)|Blocks the Start Application 1 key.|
|[LaunchApp2](Microsoft-Windows-Embedded-KeyboardFilterService-launchapp2.md)|Blocks the Start Application 1 key.|
|[LaunchMail](Microsoft-Windows-Embedded-KeyboardFilterService-launchmail.md)|Blocks the Start Mail key.|
|[LaunchMediaSelect](Microsoft-Windows-Embedded-KeyboardFilterService-launchmediaselect.md)|Blocks the Media Select key.|
|[LeftShiftLeftAltNumLock](Microsoft-Windows-Embedded-KeyboardFilterService-leftshiftleftaltnumlock.md)|Blocks the Left Shift+Left Alt+Num Lock key combination used to open the Mouse Keys dialog box.|
|[LeftShiftLeftAltPrintScreen](Microsoft-Windows-Embedded-KeyboardFilterService-leftshiftleftaltprintscreen.md)|Blocks the Left Shift+Left Alt+Print Screen key combination used to open the High Contrast dialog box.|
|[MediaNext](Microsoft-Windows-Embedded-KeyboardFilterService-medianext.md)|Blocks the Next Track key.|
|[MediaPlayPause](Microsoft-Windows-Embedded-KeyboardFilterService-mediaplaypause.md)|Blocks the Play/Pause Media key.|
|[MediaPrev](Microsoft-Windows-Embedded-KeyboardFilterService-mediaprev.md)|Blocks the Previous Track key.|
|[MediaStop](Microsoft-Windows-Embedded-KeyboardFilterService-mediastop.md)|Blocks the Stop media key.|
|[Shift](Microsoft-Windows-Embedded-KeyboardFilterService-shift.md)|Blocks both Shift keys.|
|[ShiftControlEscape](Microsoft-Windows-Embedded-KeyboardFilterService-shiftcontrolescape.md)|Blocks the Shift+Control+Escape key combination used to open Task Manager.|
|[ShiftWin](Microsoft-Windows-Embedded-KeyboardFilterService-shiftwin.md)|Blocks the Shift + Windows logo key.|
|[VolumeDown](Microsoft-Windows-Embedded-KeyboardFilterService-volumedown.md)|Blocks the Volume Down key.|
|[VolumeMute](Microsoft-Windows-Embedded-KeyboardFilterService-volumemute.md)|Blocks the Volume Mute key.|
|[VolumeUp](Microsoft-Windows-Embedded-KeyboardFilterService-volumeup.md)|Blocks the Volume Up key.|
|[Windows](Microsoft-Windows-Embedded-KeyboardFilterService-windows.md)|Blocks both Windows logo keys.|
|[WindowsB](Microsoft-Windows-Embedded-KeyboardFilterService-windowsb.md)|Blocks the Windows logo key+B key combination used to set focus in the Notification area.|
|[WindowsBreak](Microsoft-Windows-Embedded-KeyboardFilterService-windowsbreak.md)|Blocks the Windows logo key+Break key combination used to open the System dialog box.|
|[WindowsC](Microsoft-Windows-Embedded-KeyboardFilterService-windowsc.md)|Blocks the Windows logo key+C key combination used to open charms.|
|[WindowsComma](Microsoft-Windows-Embedded-KeyboardFilterService-windowscomma.md)|Blocks the Windows logo key+Comma key combination used to peek at the desktop.|
|[WindowsD](Microsoft-Windows-Embedded-KeyboardFilterService-windowsd.md)|Blocks the Windows logo key+D key combination used to show the desktop.|
|[WindowsDown](Microsoft-Windows-Embedded-KeyboardFilterService-windowsdown.md)|Blocks the Windows logo key+Down Arrow key combination used to minimize the active window.|
|[WindowsE](Microsoft-Windows-Embedded-KeyboardFilterService-windowse.md)|Blocks the Windows logo key+E key combination used to open Windows Explorer.|
|[WindowsEnter](Microsoft-Windows-Embedded-KeyboardFilterService-windowsenter.md)|Blocks the Windows logo key+Enter key combination used to start Narrator.|
|[WindowsEscape](Microsoft-Windows-Embedded-KeyboardFilterService-windowsescape.md)|Blocks the Windows logo key+Esc key combination used to close the Magnifier application.|
|[WindowsF](Microsoft-Windows-Embedded-KeyboardFilterService-windowsf.md)|Blocks the Windows logo key+F key combination used to open Search.|
|[WindowsF1](Microsoft-Windows-Embedded-KeyboardFilterService-windowsf1.md)|Blocks the Windows logo key+F1 key combination used to open Windows Help.|
|[WindowsH](Microsoft-Windows-Embedded-KeyboardFilterService-windowsh.md)|Blocks the Windows logo key+H key combination used to open the Share charm.|
|[WindowsHome](Microsoft-Windows-Embedded-KeyboardFilterService-windowshome.md)|Blocks the Windows logo key+Home key combination used to minimize or restore all inactive windows.|
|[WindowsI](Microsoft-Windows-Embedded-KeyboardFilterService-windowsi.md)|Blocks the Windows logo key+I key combination used to open the Settings charm.|
|[WindowsJ](Microsoft-Windows-Embedded-KeyboardFilterService-windowsj.md)|Blocks the Windows logo key+J key combination used to swap between snapped and filled applications.|
|[WindowsK](Microsoft-Windows-Embedded-KeyboardFilterService-windowsk.md)|Blocks the Windows logo key+K key combination used to open the Connect charm.|
|[WindowsL](Microsoft-Windows-Embedded-KeyboardFilterService-windowsl.md)|Blocks the Windows logo key+L key combination used to lock the device.|
|[WindowsLeft](Microsoft-Windows-Embedded-KeyboardFilterService-windowsleft.md)|Blocks the Windows logo key+Left Arrow key combination used to snap the active window to the left half of the screen.|
|[WindowsM](Microsoft-Windows-Embedded-KeyboardFilterService-windowsm.md)|Blocks the Windows logo key+M key combination used to minimize all windows.|
|[WindowsMinus](Microsoft-Windows-Embedded-KeyboardFilterService-windowsminus.md)|Blocks the Windows logo key+Minus key combination used to zoom out.|
|[WindowsO](Microsoft-Windows-Embedded-KeyboardFilterService-windowso.md)|Blocks the Windows logo key+O key combination used to lock device orientation.|
|[WindowsP](Microsoft-Windows-Embedded-KeyboardFilterService-windowsp.md)|Blocks the Windows logo key+P key combination used to cycle through Presentation Mode. Also blocks the Windows logo key+Shift+P and Windows logo key+Ctrl+P key combinations.|
|[WindowsPageDown](Microsoft-Windows-Embedded-KeyboardFilterService-windowspagedown.md)|Blocks the Windows logo key+Page Down key combination used to move a Microsoft Store app to the right monitor.|
|[WindowsPageUp](Microsoft-Windows-Embedded-KeyboardFilterService-windowspageup.md)|Blocks the Windows logo key+Page Up key combination used to move a Microsoft Store app to the left monitor.|
|[WindowsPeriod](Microsoft-Windows-Embedded-KeyboardFilterService-windowsperiod.md)|Blocks the Windows logo key+Period key combination used to snap the current screen to the left or right gutter. Also blocks the Windows logo key+Shift+Period key combinations.|
|[WindowsPlus](Microsoft-Windows-Embedded-KeyboardFilterService-windowsplus.md)|Blocks the Windows logo key+Plus key combination used to zoom in.|
|[WindowsQ](Microsoft-Windows-Embedded-KeyboardFilterService-windowsq.md)|Blocks the Windows logo key+Q key combination used to open the Search charm.|
|[WindowsR](Microsoft-Windows-Embedded-KeyboardFilterService-windowsr.md)|Blocks the Windows logo key+R key combination used to open the Run dialog box.|
|[WindowsRight](Microsoft-Windows-Embedded-KeyboardFilterService-windowsright.md)|Blocks the Windows logo key+Right Arrow key combination used to snap the active windows to the right half of the screen.|
|[WindowsShiftDown](Microsoft-Windows-Embedded-KeyboardFilterService-windowsshiftdown.md)|Blocks the Windows logo key+Shift+Down Arrow key combination used to minimize the active window.|
|[WindowsShiftLeft](Microsoft-Windows-Embedded-KeyboardFilterService-windowsshiftleft.md)|Blocks the Windows logo key+Shift+Left Arrow key combination used to move the active window to the left monitor.|
|[WindowsShiftRight](Microsoft-Windows-Embedded-KeyboardFilterService-windowsshiftright.md)|Blocks the Windows logo key+Shift+Right Arrow key combination used to move the active window to the right monitor.|
|[WindowsShiftUp](Microsoft-Windows-Embedded-KeyboardFilterService-windowsshiftup.md)|Blocks the Windows logo key+Shift+Up Arrow key combination used to maximize the active window vertically.|
|[WindowsSlash](Microsoft-Windows-Embedded-KeyboardFilterService-windowsslash.md)|Blocks the Windows logo key+Slash key combination used to open the Input Method Editor (IME).|
|[WindowsSpace](Microsoft-Windows-Embedded-KeyboardFilterService-windowsspace.md)|Blocks the Windows logo key+Spacebar key combination used to switch layout.|
|[WindowsT](Microsoft-Windows-Embedded-KeyboardFilterService-windowst.md)|Blocks the Windows logo key+T key combination used to set focus on taskbar and cycle through programs.|
|[WindowsTab](Microsoft-Windows-Embedded-KeyboardFilterService-windowstab.md)|Blocks the Windows logo key+Tab key combination used to cycle through Microsoft Store apps. Also blocks the Windows logo key+Ctrl+Tab and Windows logo key+Shift+Tab key combinations.|
|[WindowsU](Microsoft-Windows-Embedded-KeyboardFilterService-windowsu.md)|Blocks the Windows logo key+Comma key combination used to peek at the desktop.|
|[WindowsUp](Microsoft-Windows-Embedded-KeyboardFilterService-windowsup.md)|Blocks the Windows logo key+Up Arrow key combination used to maximize the active window.|
|[WindowsV](Microsoft-Windows-Embedded-KeyboardFilterService-windowsv.md)|Blocks the Windows logo key+V key combination used to cycle through toasts in reverse order.|
|[WindowsW](Microsoft-Windows-Embedded-KeyboardFilterService-windowsw.md)|Blocks the Windows logo key+W key combination used to open the Settings Search charm.|
|[WindowsZ](Microsoft-Windows-Embedded-KeyboardFilterService-windowsz.md)|Blocks the Windows logo key+Z key combination used to open the app bar.|

## Applies to

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Keyboard filter](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/keyboardfilter)
