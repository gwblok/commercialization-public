---
title: Customize Pen and Windows Ink
description: Customize Pen and Windows Ink settings
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 10/05/2018
ms.topic: article
ms.custom: RS5
---
# Customize Windows Pen and Ink

Customers see the the **Pen & Windows Ink** workspace when they click **Settings > Devices > Pen and Windows Ink**.

Windows provides a few means for you to customize the Pen and Ink workspace:

* You can create an advanced Pen settings app, and link to it directly within the Pen & Windows Ink Settings using Unattend.xml. See [Microsoft-Windows-TwinUI | CustomProtocol](unattend/Microsoft-Windows-TwinUI-customprotocol.md).

* You can hide the Pen shortcut settings from the Pen & Windows Ink Settings using Unattend. This is helpful for devices that are not compatible with pen settings. See [Microsoft-Windows-TwinUI | Hide](unattend/microsoft-windows-twinui-hide.md).

* You can add up to three links to your own apps to the Pen & Windows Ink settings.

* You can hide the “Ignore touch input when I’m using my pen” option within Pen & Windows Ink settings.

## Pin up to three apps in Pen & Windows Ink Settings

Starting in Windows 10, build 1703, you can pin up to three UWP apps in the frequently used apps section of the Windows Ink Workspace. You do this by creating an xml file called `InkWorkspaceModification.xml` and placing it in the following directory: `%SystemDrive%\Users\Default\AppData\Local\Microsoft\Windows\Shell`.

In the `InkWorkspaceModification.xml` file, you link to UWP apps by creating a Tile element and providing the `AppUserModelID`. If you are using desktop apps instead, you'd add a `DesktopApplicationTile` element and provide the LinkFilePath.

```xml
<?xml version="1.0" encoding="utf-8"?>
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
 xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    xmlns:taskbar="http://schemas.microsoft.com/Start/2014/TaskbarLayout"
    Version="1">
  <InkWorkspaceTopApps>
    <Tile AppUserModelID="Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe!App"/>
    <Tile AppUserModelID="Microsoft.WindowsCalculator_8wekyb3d8bbwe!App"/>
    <DesktopApplicationTile LinkFilePath="%APPDATA%\Microsoft\Windows\Start Menu\Programs\OneDrive.lnk"/>
</InkWorkspaceTopApps>
</LayoutModificationTemplate>
```

## Hide the “Ignore touch input when I’m using my pen” setting

In Windows 10, build 1703, you have the option to hide the **Ignore touch input when I’m using my pen** setting if the device doesn’t accept touch and pen input simultaneously. 

![Screenshot of Pen and Windows Ink settings](../images/pen-and-ink.png)

To hide the simultaneous pen and touch settings UI, create the following registry key as a DWORD and set it to a 1. Setting it to 0 (default) will show the setting again.

`HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Pen\HideSPTSettings`
