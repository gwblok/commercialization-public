---
title: Microsoft-Windows-Shell-Setup
description: Microsoft-Windows-Shell-Setup
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: eeac1b17-6ef9-4ba6-9888-7adf9387ec04
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-Shell-Setup

Microsoft-Windows-Shell-Setup contains elements and settings that control how the Windows operating system shell is installed on a destination computer.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
|[AutoLogon](microsoft-windows-shell-setup-autologon.md)|Specifies credentials for an account that is used to automatically log on to the computer.|
|[BluetoothTaskbarIconEnabled](microsoft-windows-shell-setup-bluetoothtaskbariconenabled.md)|Specifies whether to enable the Bluetooth taskbar icon.|
|[ComputerName](microsoft-windows-shell-setup-computername.md)|Specifies the name of the computer.|
|[ConvertibleSlateModePromptPreference](microsoft-windows-shell-setup-convertibleslatemodepromptpreference.md)|Configure to support prompts triggered by changes to [ConvertibleSlateMode](microsoft-windows-gpiobuttons-convertibleslatemode.md). OEMs must make sure that ConvertibleSlateMode is always accurate for their devices.|
|[CopyProfile](microsoft-windows-shell-setup-copyprofile.md)|Specifies whether the default user profile that is normally stored in the C:\Users\Default User folder is overwritten by copying the current user's profile.|
|[DisableAutoDaylightTimeSet](microsoft-windows-shell-setup-disableautodaylighttimeset.md)|Specifies whether to enable the destination computer to automatically change between daylight saving time and standard time.|
|[Display](microsoft-windows-shell-setup-display.md)|Specifies display settings to apply to a destination computer.|
|[FirstLogonCommands](microsoft-windows-shell-setup-firstlogoncommands.md)|Specifies commands to run the first time that an end user logs on to the computer. This setting is not supported in Windows 10 in S mode. |
|[FolderLocations](microsoft-windows-shell-setup-folderlocations.md)|Specifies the location of the user profile and program data folders.<br/> <strong>Important: </strong>This setting should be used only in a test environment. If you change the default location of the user profile directories or program data folders to a volume other than the system volume, you cannot service your image.|
|[LogonCommands](microsoft-windows-shell-setup-logoncommands.md)|Specifies commands to run when an end user logs on to the computer.|
|[NotificationArea](microsoft-windows-shell-setup-notificationarea.md)|Specifies settings that are related to the system notification area at the far right of the taskbar.|
|[OEMInformation](microsoft-windows-shell-setup-oeminformation.md)|Specifies information about the OEM, including the name, the model of the computer, and a logo for the OEM.|
|[OEMName](microsoft-windows-shell-setup-oemname.md)|Specifies the name of the OEM for the group or groups of app tiles that you pin to the Start screen.|
|[OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md)|Specifies local accounts to be created, domain accounts to be added, and the administrator password.|
|[OOBE](microsoft-windows-shell-setup-oobe.md)|Specifies values that suppress certain pages of OOBE.|
|[ProductKey](microsoft-windows-shell-setup-productkey.md)|Specifies the product key for the Windows edition.|
|[RegisteredOrganization](microsoft-windows-shell-setup-registeredorganization.md)|Specifies information about the computer's owner.|
|[RegisteredOwner](microsoft-windows-shell-setup-registeredowner.md)|Specifies information about the organization of the computer's owner.|
|[ShowPowerButtonOnStartScreen](microsoft-windows-shell-setup-showpowerbuttononstartscreen.md)|Specifies that the Power Options button is visible on the Start screen.|
|[SignInMode](microsoft-windows-shell-setup-signinmode.md)|Specifies whether users switch to tablet mode by default after signing in.|
|[StartTiles](microsoft-windows-shell-setup-starttiles.md)|Specifies the position of up to 24 app tiles on the Start screen, and one app badge on the Lock screen.|
|[TaskbarLinks](microsoft-windows-shell-setup-taskbarlinks.md)|Specifies shortcuts to display on the taskbar. You can specify up to three links.|
|[Themes](microsoft-windows-shell-setup-themes.md)|Specifies custom elements of the Windows visual style.|
|[TimeZone](microsoft-windows-shell-setup-timezone.md)|Specifies the computer's time zone.|
|[UserAccounts](microsoft-windows-shell-setup-useraccounts.md)|Specifies local accounts to be created or domain accounts to be added during installation.|
|[VisualEffects](microsoft-windows-shell-setup-visualeffects.md)|Specifies additional display settings.|
|[WindowsFeatures](microsoft-windows-shell-setup-windowsfeatures.md)|Specifies whether to show entry points for Internet Explorer, Media Center, and Windows Media Player.|

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
