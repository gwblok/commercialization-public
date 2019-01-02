---
title: Changed answer file settings for previous Windows 10 builds
description: This topic shows the historic list of changes to answer file settings for each build of Windows 10.
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 04/30/2018
ms.topic: article


---

# Changed answer file settings for previous Windows 10 builds

This topic shows the historic list of changes to answer file settings for each build of Windows 10.

## Changed answer file settings for Windows 10 for desktop editions, build 1709

Below are the Windows 10, version 1709 answer file settings that have changed since Windows 10 for desktop editions (Home, Pro, Enterprise, and Education), version 1703.

### New Windows settings

| Setting name         | Description                                                                      |
|:---------------------|:---------------------------------------------------------------------------------|
| [Microsoft-Windows-Shell-Setup-OEMInformation-SupportProvider](microsoft-windows-shell-setup-oeminformation-supportprovider.md)           | New. Specifies the name of the OEM support app or website to display in the Get Help app. If not provided, the default System Manufacturer name (from msinfo32.exe) will be used. |
| [Microsoft-Windows-Embedded-UnifiedWriteFilter-OverlayFlags](microsoft-windows-embedded-unifiedwritefilter-overlayflags.md)           | New. Specifies whether writes to unused space on the volume are allowed to pass through, rather than being redirected to the overlay. |
| [Microsoft-Windows-WorkstationService-AllowInsecureGuestAuth](microsoft-windows-workstationservice-allowinsecureguestauth.md)           | New. Specifies whether an SMB client allows insecure guest logons to an SMB server. Microsoft recommends using the default value of `0`. |

### Deprecated Windows settings

| Setting name                                           | Description                                                                      |
|:-------------------------------------------------------|:---------------------------------------------------------------------------------|
| [Microsoft-Windows-Shell-Setup-OEMInformation-HelpCustomized](microsoft-windows-shell-setup-oeminformation-helpcustomized.md)             | Deprecated. Setting this no longer has any impact. To [customize the Get Help app](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/customize-get-help-app), define `SupportURL` or `SupportAppURL` as part of your `OEMInformation`.                                                                                                                      |
| [Microsoft-Windows-Shell-Setup-OEMInformation-Logo](microsoft-windows-shell-setup-oeminformation-logo.md)                                 | Deprecated as no OEM logo is displayed in the Get Help app.                                                                                            |
| [Microsoft-Windows-Shell-Setup-OEMInformation-SupportHours](microsoft-windows-shell-setup-oeminformation-supporthours.md)                 | Deprecated as no OEM support hours are displayed in the Get Help app.                                                                                  |
| [Microsoft-Windows-Shell-Setup-OEMInformation-SupportPhone](microsoft-windows-shell-setup-oeminformation-supportphone.md)                 | Deprecated as no OEM support phone number is displayed in the Get Help app.                                                                            |
| [Microsoft-Windows-Shell-Setup-OEMInformation-Model](microsoft-windows-shell-setup-oeminformation-model.md)                               | Deprecated. The Model name displayed in the Get Help app is now based on your System Product Name value, as defined in System Information (msinfo.exe). |
| [Microsoft-Windows-Shell-Setup-OEMInformation-Manufacturer](microsoft-windows-shell-setup-oeminformation-manufacturer.md)                 | Deprecated. The Manufacturer name displayed in the Get Help app is now based on your System Manufacturer value, as defined in System Information (msinfo.exe), unless you provide a `SupportProvider` parameter as part of your `OEMInformation`. When `SupportProvider` is provided, it will override the System Manufacturer name. For this release, if `SupportProvider` is not present but the deprecated value `Manufacturer` is, it will still be used to support upgrade scenarios. |

### Removed Windows settings

| Setting name                                           | Description                                                                      |
|:-------------------------------------------------------|:---------------------------------------------------------------------------------|
| [Microsoft-Windows-Shell-Setup-VisualEffects-FontSmoothing](microsoft-windows-shell-setup-visualeffects-fontsmoothing.md)                 | This previously deprecated setting is now removed.                                                                                               |
| [Microsoft-Windows-Shell-Setup-Themes-ScreenSaver](microsoft-windows-shell-setup-themes-screensaver.md)                                   | ScreenSaver functionality in Themes is removed. ScreenSaver is deprecated in Group Policy, Control Panel, and SysPrep. Lockscreen features and policies are preferred over using ScreenSaver. We recommend using automatic power plans to dim the screen. This can help reduce system power consumption.          |

## Changed answer file settings for Windows 10 for desktop editions, build 1703

Below are the Windows 10, version 1703 answer-file settings that changed since Windows 10 for desktop editions (Home, Pro, Enterprise, and Education), Build 1607.

### New Windows Settings

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>New setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td><p><a href="microsoft-windows-tpm-tasks-cleartpm.md" data-raw-source="[Microsoft-Windows-TPM-Tasks-ClearTpm](microsoft-windows-tpm-tasks-cleartpm.md)">Microsoft-Windows-TPM-Tasks-ClearTpm</a></p></td>
<td><p>New. Specifies whether to clear the Trusted Platform Module (TPM) during Windows setup. Clearing the TPM prevents an issue in earlier versions that kept some Windows features from working if the TPM was incorrectly set.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-twinui-hide.md" data-raw-source="[Microsoft-Windows-TwinUI-Hide](microsoft-windows-twinui-hide.md)">Microsoft-Windows-TwinUI-Hide</a></p></td>
<td><p>New. Specifies whether to hide the link to an advanced settings app in the Pen and Windows Ink Settings page.</p></td>
</tr>
</tbody>
</table>

## Changed answer file settings for Windows 10 for desktop editions, build 1607

The tables below describe Windows 10, version 1607 answer-file settings that changed since Windows 10 for desktop editions (Home, Pro, Enterprise, and Education), Build 1511.

### <a href="" id="newwindowsettings"></a>New Windows Settings

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>New setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="Microsoft-Windows-RemoteAssistance-Exe-fenablechatcontrol.md" data-raw-source="[Microsoft-Windows-RemoteAssistance-Exe-fEnableChatControl](Microsoft-Windows-RemoteAssistance-Exe-fenablechatcontrol.md)">Microsoft-Windows-RemoteAssistance-Exe-fEnableChatControl</a></p></td>
<td><p>New.</p></td>
</tr>
<tr class="even">
<td><p><a href="Microsoft-Windows-Shell-Setup-enablestartmenu.md" data-raw-source="[Microsoft-Windows-Shell-Setup-EnableStartMenu](Microsoft-Windows-Shell-Setup-enablestartmenu.md)">Microsoft-Windows-Shell-Setup-EnableStartMenu</a></p></td>
<td><p>New. Specifies whether the Start menu is enabled and users can click on it.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-desktopoptimization-gotodesktoponsignin.md" data-raw-source="[Microsoft-Windows-Shell-Setup-DesktopOptimization-GoToDesktopOnSignIn](microsoft-windows-shell-setup-desktopoptimization-gotodesktoponsignin.md)">Microsoft-Windows-Shell-Setup-DesktopOptimization-GoToDesktopOnSignIn</a></p></td>
<td><p>New. Specifies to go to the desktop instead of Start Screen when signing in or when all the apps on a screen are closed.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-desktopoptimization-showwindowsstoreappsontaskbar.md" data-raw-source="[Microsoft-Windows-Shell-Setup-DesktopOptimization-ShowWindowsStoreAppsOnTaskbar](microsoft-windows-shell-setup-desktopoptimization-showwindowsstoreappsontaskbar.md)">Microsoft-Windows-Shell-Setup-DesktopOptimization-ShowWindowsStoreAppsOnTaskbar</a></p></td>
<td><p>New. Shows Window Store apps on taskbar.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile7.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile7](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile7.md)">Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile7</a> thru <a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile12.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile12](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile12.md)">Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile12</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> menu, in the given position 7-12.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile7-appidorpath.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareTiles-SquareorDesktopTile7-AppIdOrPath](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile7-appidorpath.md)">Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareTiles-SquareorDesktopTile7-AppIdOrPath</a> thru <a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile12-appidorpath.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareTiles-SquareorDestopTile12-AppIdOrPath](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile12-appidorpath.md)">Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareTiles-SquareorDestopTile12-AppIdOrPath</a></p></td>
<td><p>Specifies the <code>AppID</code> of the Microsoft Store apps, or the path to the desktop apps that appear as square tiles on the <strong>Start</strong> screen.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile7-firstruntask.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile7-FirstRunTask](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile7-firstruntask.md)">Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile7-FirstRunTask</a> through <a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile12-firstruntask.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile12-FirstRunTask](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile12-firstruntask.md)">Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile12-FirstRunTask</a></p></td>
<td><p>Specifies the background task that is active, or live, by default for a tile when a user signs in to Windows for the first time.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile7.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOveride-SquareTiles-SquareorDesktopTile7](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile7.md)">Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOveride-SquareTiles-SquareorDesktopTile7</a> thru <a href="microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile12.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOveride-SquareTiles-SquareorDesktopTile12](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile12.md)">Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOveride-SquareTiles-SquareorDesktopTile12</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> menu, in the given position 7-12</p>
<p>If the region of the current user account is among those in the Start Tile regional overrides, you can use this setting. For more information, see <a href="microsoft-windows-shell-setup-starttiles-regionaloverrides.md" data-raw-source="[RegionalOverrides](microsoft-windows-shell-setup-starttiles-regionaloverrides.md)">RegionalOverrides</a>.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile7-appidorpath.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOveride-SquareTiles-SquareorDesktopTile7-AppIdOrPath](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile7-appidorpath.md)">Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOveride-SquareTiles-SquareorDesktopTile7-AppIdOrPath</a> thru <a href="microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile12-appidorpath.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOveride-SquareTiles-SquareorDesktopTile12-AppIdOrPath](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squareordesktoptile12-appidorpath.md)">Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOveride-SquareTiles-SquareorDesktopTile12-AppIdOrPath</a></p></td>
<td><p>Specifies the <code>AppID</code> of the Microsoft Store apps, or the path to the desktop apps that appear as square tiles on the <strong>Start</strong> screen.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile7-firstruntask.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOveride-SquareTiles-SquareTile7-FirstRunTask](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile7-firstruntask.md)">Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOveride-SquareTiles-SquareTile7-FirstRunTask</a> thru <a href="microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile12-firstruntask.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOveride-SquareTiles-SquareTiles-SquareTile12-FirstRunTask](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-squaretiles-squaretile12-firstruntask.md)">Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOveride-SquareTiles-SquareTiles-SquareTile12-FirstRunTask</a></p></td>
<td><p>Specifies the background task that is active, or live, by default for a tile when a user signs in to Windows for the first time.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-themes-uwpappsuselighttheme.md" data-raw-source="[Microsoft-Windows-Shell-Setup-Themes-UWPAppsUseLightTheme](microsoft-windows-shell-setup-themes-uwpappsuselighttheme.md)">Microsoft-Windows-Shell-Setup-Themes-UWPAppsUseLightTheme</a></p></td>
<td><p>Specifies whether the dark mode is applied.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-twinui-customprotocol.md" data-raw-source="[Microsoft-Windows-TwinUI-CustomProtocol](microsoft-windows-twinui-customprotocol.md)">Microsoft-Windows-TwinUI-CustomProtocol</a></p></td>
<td><p>Specifies advanced pen settings.</p></td>
</tr>
</tbody>
</table>

### <a href="" id="renamedordeprecatedsettings"></a>Deprecated Windows Settings

| Deprecated setting                                                               | Status or recomendation for Windows 10, version 1607                                               |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| [Microsoft-Windows-WiFiNetworkManager](microsoft-windows-wifinetworkmanager.md) | The Wi-Fi Sense credential sharing feature has been removed. This setting no longer does anything. |

### <a href="" id="removedsettings"></a>Removed Windows Settings

The following settings are no longer available in Windows 10, version 1607:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Removed setting from Windows 8 or Windows Server 2012</th>
<th>Recommendation for Windows 10, version 1607</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="microsoft-windows-mobilepc-sensors-api.md" data-raw-source="[microsoft-windows-mobilepc-sensors-api-](microsoft-windows-mobilepc-sensors-api.md)">microsoft-windows-mobilepc-sensors-api-</a>\SensorPermissions\Sensor\Enable</p></td>
<td><p>The setting and its ancestor elements have been removed.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-mobilepc-sensors-api.md" data-raw-source="[microsoft-windows-mobilepc-sensors-api-](microsoft-windows-mobilepc-sensors-api.md)">microsoft-windows-mobilepc-sensors-api-</a>\SensorPermissions\Sensor\GUID</p></td>
<td><p>The setting and its ancestor elements have been removed.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-mobilepc-sensors-api.md" data-raw-source="[microsoft-windows-mobilepc-sensors-api-](microsoft-windows-mobilepc-sensors-api.md)">microsoft-windows-mobilepc-sensors-api-</a>\SensorPermissions\Sensor\GUIDClassification</p></td>
<td><p>The setting and its ancestor elements have been removed.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-mobilepc-sensors-api.md" data-raw-source="[microsoft-windows-mobilepc-sensors-api-](microsoft-windows-mobilepc-sensors-api.md)">microsoft-windows-mobilepc-sensors-api-</a>\SensorPermissions\Sensor\Order</p></td>
<td><p>The setting and its ancestor elements have been removed.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-securestartup-filterdriver.md" data-raw-source="[microsoft-windows-securestartup-filterdriver-](microsoft-windows-securestartup-filterdriver.md)">microsoft-windows-securestartup-filterdriver-</a>\InPlaceCrypto</p></td>
<td><p>The setting has been removed.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-securestartup-filterdriver.md" data-raw-source="[microsoft-windows-securestartup-filterdriver-](microsoft-windows-securestartup-filterdriver.md)">microsoft-windows-securestartup-filterdriver-</a>\ModifiedWriteMaximum</p></td>
<td><p>The setting has been removed.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-securestartup-filterdriver.md" data-raw-source="[microsoft-windows-securestartup-filterdriver-](microsoft-windows-securestartup-filterdriver.md)">microsoft-windows-securestartup-filterdriver-</a> \ReadDoubleBuffering</p></td>
<td><p>The setting has been removed.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://docs.microsoft.com/en-us/windows/configuration/wcd/wcd-policies#textinput" data-raw-source="[TextInput](https://docs.microsoft.com/en-us/windows/configuration/wcd/wcd-policies#textinput)">TextInput</a>\AllowKoreanExtendedHanja</p></td>
<td><p>The setting has been removed.</p></td>
</tr>
</tbody>
</table>

### <a href="" id="removediesettings"></a>Removed Internet Explorer Settings

These settings in the [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) component are removed:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Removed setting from Windows 8 or Windows Server 2012</th>
<th>Recommendation for Windows 10, version 1607</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="microsoft-windows-ie-internetexplorer.md" data-raw-source="[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)">Microsoft-Windows-IE-InternetExplorer</a>\AllSitesCompatibilityMode</p></td>
<td><p>The setting has been removed.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-ie-internetexplorer.md" data-raw-source="[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)">Microsoft-Windows-IE-InternetExplorer</a>\DisableWelcomePage</p></td>
<td><p>The setting has been removed.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-ie-internetexplorer.md" data-raw-source="[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)">Microsoft-Windows-IE-InternetExplorer</a>\NoDial</p></td>
<td><p>The setting has been removed.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-ie-internetexplorer.md" data-raw-source="[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)">Microsoft-Windows-IE-InternetExplorer</a>\ShowCompatibilityViewButton</p></td>
<td><p>The setting has been removed.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-ie-internetexplorer.md" data-raw-source="[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)">Microsoft-Windows-IE-InternetExplorer</a>\SmallCommandBarIcons</p></td>
<td><p>The setting has been removed.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-ie-internetexplorer.md" data-raw-source="[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)">Microsoft-Windows-IE-InternetExplorer</a>\Scope\DisplayQuickPick</p></td>
<td><p>The setting has been removed.</p></td>
</tr>
</tbody>
</table>

## Changed answer file settings for Windows 10 for desktop editions, build 1511

The tables below describe Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) and Windows Server 2016 answer file settings that changed since Windows 8.1 Update, Windows 8.1, and Windows Server 2012 R2.

### <a href="" id="newwindowssettings"></a>New Windows settings

These Unattend settings are new in Windows 10:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>New setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft-Windows-Setup-ImageInstall-OSImage-Compact</p></td>
<td><p>Specifies whether the Windows image should be applied with compression enabled during installation. If set to <strong>true</strong>, files written to the disk during installation are compressed individually, which allows Windows to take up less disk space.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-wlansvc-coexistencesupport.md" data-raw-source="[Microsoft-Windows-Wlansvc-CoexistenceSupport](microsoft-windows-wlansvc-coexistencesupport.md)">Microsoft-Windows-Wlansvc-CoexistenceSupport</a></p></td>
<td><p>Specifies the type of co-existence that&#39;s supported on the device:</p>
<ul>
<li><strong>Both</strong> - Both Wi-Fi and Bluetooth work at the same performance level during co-existence.</li>
<li><strong>Wi-Fi reduced</strong> - On a 2X2 system, Wi-Fi performance is reduced to 1X1 level.</li>
<li><strong>Bluetooth centered</strong> - When co-existing, Bluetooth has priority and restricts Wi-Fi performance.</li>
<li><strong>One</strong> - Either Wi-Fi or Bluetooth will stop working.</li>
</ul></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-wlansvc-numantennaconnected.md" data-raw-source="[Microsoft-Windows-Wlansvc-NumAntennaConnected](microsoft-windows-wlansvc-numantennaconnected.md)">Microsoft-Windows-Wlansvc-NumAntennaConnected</a></p></td>
<td><p>Specifies the number of antennas that are connected to the WLAN radio.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-wlansvc-simultaneousmultichannelsupported.md" data-raw-source="[Microsoft-Windows-Wlansvc-SimultaneousMultiChannelSupported](microsoft-windows-wlansvc-simultaneousmultichannelsupported.md)">Microsoft-Windows-Wlansvc-SimultaneousMultiChannelSupported</a></p></td>
<td><p>Specifies the maximum number of channels that the Wi-Fi device can simultaneously operate on. For example, you can use this to specify support for Station mode and Wi-Fi Direct GO on separate channels simultaneously.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-wlansvc-wlanfunctionleveldeviceresetsupported.md" data-raw-source="[Microsoft-Windows-Wlansvc-WLANFunctionLevelDeviceResetSupported](microsoft-windows-wlansvc-wlanfunctionleveldeviceresetsupported.md)">Microsoft-Windows-Wlansvc-WLANFunctionLevelDeviceResetSupported</a></p></td>
<td><p>Specifies whether the device supports functional level device reset. The functional level device reset feature in the OS checks this system capability exclusively to determine if it can run.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-wlansvc-wlanplatformleveldeviceresetsupported.md" data-raw-source="[Microsoft-Windows-Wlansvc-WLANPlatformLevelDeviceResetSupported](microsoft-windows-wlansvc-wlanplatformleveldeviceresetsupported.md)">Microsoft-Windows-Wlansvc-WLANPlatformLevelDeviceResetSupported</a></p></td>
<td><p>Specifies whether the device supports platform level device reset. The platform level device reset feature in the OS checks this system capability exclusively to determine if it can run.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-deviceaccess-setregionspecificprivacyaccesspolicy.md" data-raw-source="[Microsoft-Windows-DeviceAccess-SetRegionSpecificPrivacyAccessPolicy](microsoft-windows-deviceaccess-setregionspecificprivacyaccesspolicy.md)">Microsoft-Windows-DeviceAccess-SetRegionSpecificPrivacyAccessPolicy</a></p></td>
<td><p>The <code>Microsoft-Windows-DeviceAccess</code> component specifies settings for enabling device policy, which includes enabling the China CTA policy through the <code>SetRegionSpecificPrivacyAccessPolicy</code> setting.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-printing-spooler-core-start.md" data-raw-source="[Microsoft-Windows-Printing-Spooler-Core-Start](microsoft-windows-printing-spooler-core-start.md)">Microsoft-Windows-Printing-Spooler-Core-Start</a></p></td>
<td><p>Indicates whether the spooler autologger will start by default when the system boots.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-printing-spooler-core-removempdw.md" data-raw-source="[Microsoft-Windows-Printing-Spooler-Core-RemoveMPDW](microsoft-windows-printing-spooler-core-removempdw.md)">Microsoft-Windows-Printing-Spooler-Core-RemoveMPDW</a></p></td>
<td><p>Specifies whether to remove the Microsoft Print to PDF print queue and driver package from a Windows installation.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-oeminformation-supportappurl.md" data-raw-source="[Microsoft-Windows-Shell-Setup-OEMInformation-SupportAppURL](microsoft-windows-shell-setup-oeminformation-supportappurl.md)">Microsoft-Windows-Shell-Setup-OEMInformation-SupportAppURL</a></p></td>
<td><p>Specifies the OEM-built support app that will be launched instead of the web URL.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-offlineuseraccounts.md" data-raw-source="[Microsoft-Windows-Shell-Setup-OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md)">Microsoft-Windows-Shell-Setup-OfflineUserAccounts</a></p></td>
<td><p>Specifies the account information used to join a domain during Windows Setup.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-unattendedjoin-offlineidentification.md" data-raw-source="[Microsoft-Windows-UnattendedJoin-OfflineIdentification](microsoft-windows-unattendedjoin-offlineidentification.md)">Microsoft-Windows-UnattendedJoin-OfflineIdentification</a></p></td>
<td><p>Specifies credentials for provisioning the account data during the offlineServicing configuration pass.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-oobe-unattendenableretaildemo.md" data-raw-source="[Microsoft-Windows-Shell-Setup-OOBE-UnattendEnableRetailDemo](microsoft-windows-shell-setup-oobe-unattendenableretaildemo.md)">Microsoft-Windows-Shell-Setup-OOBE-UnattendEnableRetailDemo</a></p></td>
<td><p>Enables retail demo mode on the device. Retail demo mode is a special retail mode that can be activated in retail stores to run a demo on the device. The demo highlights key features of the OS and shows off the device user experience.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-oobe-vmmodeoptimizations.md" data-raw-source="[Microsoft-Windows-Shell-Setup-OOBE-VMModeOptimizations](microsoft-windows-shell-setup-oobe-vmmodeoptimizations.md)">Microsoft-Windows-Shell-Setup-OOBE-VMModeOptimizations</a></p></td>
<td><p>Specifies settings you can use to customize the user experience when in VM mode.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-signinmode.md" data-raw-source="[Microsoft-Windows-Shell-Setup-SignInMode](microsoft-windows-shell-setup-signinmode.md)">Microsoft-Windows-Shell-Setup-SignInMode</a></p>
<p><a href="microsoft-windows-shell-setup-convertibleslatemodepromptpreference.md" data-raw-source="[Microsoft-Windows-Shell-Setup-ConvertibleSlateModePromptPreference](microsoft-windows-shell-setup-convertibleslatemodepromptpreference.md)">Microsoft-Windows-Shell-Setup-ConvertibleSlateModePromptPreference</a></p></td>
<td><p>OEMs can configure these settings to support Continuum, which is a new, adaptive user experience in Windows 10 that optimizes the look and behavior of apps and the Windows UI for a given physical form factor and the customer&#39;s usage preferences.</p>
<ul>
<li><p>To configure devices to boot straight into tablet mode, use <code>SignInMode</code>.</p></li>
<li><p>To support prompts triggered by changes to <a href="microsoft-windows-gpiobuttons-convertibleslatemode.md" data-raw-source="[ConvertibleSlateMode](microsoft-windows-gpiobuttons-convertibleslatemode.md)">ConvertibleSlateMode</a>, configure <code>ConvertibleSlateModePromptPreference</code>. OEMs must make sure that <code>ConvertibleSlateMode</code> is always accurate for their devices.</p></li>
</ul>
<p>OEMs may also specify the device form factor using <code>DeviceForm</code>.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-deployment-deviceform.md" data-raw-source="[Microsoft-Windows-Deployment-DeviceForm](microsoft-windows-deployment-deviceform.md)">Microsoft-Windows-Deployment-DeviceForm</a></p></td>
<td><p>Use to specify the device form factor running Windows 10.</p>
<p>OEMs must set <code>DeviceForm</code> correctly to support the following features or components:</p>
<ul>
<li><strong>Retail demo mode</strong> - Relies on the setting value to dictate the demo content that will be shown on the device. For example, if an OEM wants to highlight Continuum, the OEM must accurately configure the value for <code>DeviceForm</code>.</li>
<li><strong>Cortana and Bing</strong> - Use the <code>DeviceForm</code> value to determine the accuracy of specific signals, such as location (GPS versus Wi-Fi versus reverse IP address lookup).</li>
<li>Windows 10 features - Some OS functionality, such as Bluetooth and camera, may require <code>DeviceForm</code> to be accurately configured for full functionality.</li>
</ul></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-tabletpc-platform-input-core-handwritingpaneldockedmodeset.md" data-raw-source="[Microsoft-Windows-TabletPC-Platform-Input-Core-HandwritingPanelDockedModeSet](microsoft-windows-tabletpc-platform-input-core-handwritingpaneldockedmodeset.md)">Microsoft-Windows-TabletPC-Platform-Input-Core-HandwritingPanelDockedModeSet</a></p></td>
<td><p>Use to specify whether the handwriting panel is initially docked by default.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-tabletpc-platform-input-core-touchkeyboardautoinvokeenabled.md" data-raw-source="[Microsoft-Windows-TabletPC-Platform-Input-Core-TouchKeyboardAutoInvokeEnabled](microsoft-windows-tabletpc-platform-input-core-touchkeyboardautoinvokeenabled.md)">Microsoft-Windows-TabletPC-Platform-Input-Core-TouchKeyboardAutoInvokeEnabled</a></p></td>
<td><p>Use to specify whether the touch keyboard is automatically invoked by default when there is no hardware keyboard connected and the device is in non-tablet mode.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-mapcontrol-desktop-chinavariantwin10.md" data-raw-source="[Microsoft-Windows-MapControl-Desktop-ChinaVariantWin10](microsoft-windows-mapcontrol-desktop-chinavariantwin10.md)">Microsoft-Windows-MapControl-Desktop-ChinaVariantWin10</a></p></td>
<td><p>Use to specify that the Windows device is intended to ship in China. When enabled, maps approved by the State Bureau of Surveying and Mapping in China are used, which are obtained from a server located in China.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-deviceguard-unattend.md" data-raw-source="[Microsoft-Windows-DeviceGuard-Unattend](microsoft-windows-deviceguard-unattend.md)">Microsoft-Windows-DeviceGuard-Unattend</a></p></td>
<td><p>Specifies settings for initializing and enforcing virtualization-based security, which helps protect system memory and kernel mode apps and drivers from possible tampering.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-embedded-bootexp.md" data-raw-source="[Microsoft-Windows-Embedded-BootExp](microsoft-windows-embedded-bootexp.md)">Microsoft-Windows-Embedded-BootExp</a></p></td>
<td><p>Specifies settings you can use to suppress OS elements that appear when the device starts or resumes, or you can suppress the crash screen when the OS encounters an error that it cannot recover from.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-embedded-embeddedlogon.md" data-raw-source="[Microsoft-Windows-Embedded-EmbeddedLogon](microsoft-windows-embedded-embeddedlogon.md)">Microsoft-Windows-Embedded-EmbeddedLogon</a></p></td>
<td><p>Specifies settings that you can use to suppress UI elements that relate to the Welcome screen and shutdown screen.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-embedded-shelllauncher.md" data-raw-source="[Microsoft-Windows-Embedded-ShellLauncher](microsoft-windows-embedded-shelllauncher.md)">Microsoft-Windows-Embedded-ShellLauncher</a></p></td>
<td><p>Specifies settings you can use to replace the default OS shell with a custom shell.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-embedded-unifiedwritefilter.md" data-raw-source="[Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md)">Microsoft-Windows-Embedded-UnifiedWriteFilter</a></p></td>
<td><p>Use unified write filter (UWF) settings in your enterprise device to help protect your physical storage media.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-wifinetworkmanager.md" data-raw-source="[Microsoft-Windows-WiFiNetworkManager](microsoft-windows-wifinetworkmanager.md)">Microsoft-Windows-WiFiNetworkManager</a></p></td>
<td><p>Specifies settings that you can configure for Wi-Fi Sense.</p></td>
</tr>
</tbody>
</table>

### <a href="" id="changedwindowssettings"></a>Changed Windows settings

These Windows 10 for desktop editions and Windows Server 2016 settings have changed from Windows 8.1 Update, Windows 8.1, and Windows Server 2012 R2:

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Changed setting</th>
<th>Description of setting</th>
<th>Description of change</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-computername.md" data-raw-source="[Microsoft-Windows-Shell-Setup-ComputerName](microsoft-windows-shell-setup-computername.md)">Microsoft-Windows-Shell-Setup-ComputerName</a></p></td>
<td><p>Specifies the computer name used to access the computer from the network.</p></td>
<td><p>Added offlineServicing to the list of valid configuration passes.</p>
<p>In Windows 10, users can no longer enter a computer name during OOBE as the name is auto-generated. To set a default computer name pre-OOBE, OEMs can configure <code>ComputerName</code> in the unattend file and specify a name for the computer.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-oobe-protectyourpc.md" data-raw-source="[Microsoft-Windows-Shell-Setup-OOBE-ProtectYourPC](microsoft-windows-shell-setup-oobe-protectyourpc.md)">Microsoft-Windows-Shell-Setup-OOBE-ProtectYourPC</a></p></td>
<td><p>Specifies whether Express settings are used.</p></td>
<td><p>Updated the description for the setting as well as the list of valid values and their descriptions for the values.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-autologon.md" data-raw-source="[Microsoft-Windows-Shell-Setup-AutoLogon](microsoft-windows-shell-setup-autologon.md)">Microsoft-Windows-Shell-Setup-AutoLogon</a></p></td>
<td><p>Specifies the account to use to log on to a computer automatically.</p></td>
<td><p>Added an important note that in Windows 10, if you configure <code>AutoLogon</code> the OS will skip the user account creation phase during OOBE and the account creation phase during OOBE is skipped in all versions of Windows when at least one user account is created through the <code>UserAccounts</code> section of the same unattend file.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-firstlogoncommands.md" data-raw-source="[Microsoft-Windows-Shell-Setup-FirstLogonCommands](microsoft-windows-shell-setup-firstlogoncommands.md)">Microsoft-Windows-Shell-Setup-FirstLogonCommands</a></p></td>
<td><p>Starts a command or script after the user completes OOBE.</p></td>
<td><p>This command now works like <a href="microsoft-windows-shell-setup-logoncommands.md" data-raw-source="[LogonCommands\AsynchronousCommand](microsoft-windows-shell-setup-logoncommands.md)">LogonCommands\AsynchronousCommand</a>: all commands using these unattend settings are now started at the same time, and no longer wait for the previous command to finish. </p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-deployment-reseal.md" data-raw-source="[Microsoft-Windows-Deployment-Reseal](microsoft-windows-deployment-reseal.md)">Microsoft-Windows-Deployment-Reseal</a></p></td>
<td><p>Indicates whether the computer runs in audit mode or Windows OOBE when the computer is next started.</p></td>
<td><p>Prior to Windows 10, <code>Reseal</code> was a special-case setting which caused all other settings in the same configuration pass to be skipped when specified in the auditSystem or oobeSystem configuration passes. In Windows 10, Reseal is always processed after all other settings in the same configuration pass.</p>
<p>For the &quot;auditSystem Audit true&quot; row, this scenario is now supported and the Result column has been updated.</p>
<p>For the &quot;oobeSystem OOBE true&quot; row, this scenario is now supported and the Result column has been updated.</p></td>
</tr>
</tbody>
</table>

### <a href="" id="renamedordeprecatedsettings"></a>Deprecated Windows settings

The following Windows 8.1 Update, Windows 8.1, and Windows Server 2012 R2 settings are not supported in Windows 10 for desktop editions or Windows Server 2016 , and may be removed in a future release. The following table includes status of the setting, and recommendations for new settings to use when applicable:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Deprecated setting from Windows 8.1 or Windows Server 2012 R2</th>
<th>Status or recommendation for Windows 10 for desktop editions or Windows Server 2016</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-oobe-networklocation.md" data-raw-source="[Microsoft-Windows-Shell-Setup-OOBE-NetworkLocation](microsoft-windows-shell-setup-oobe-networklocation.md)">Microsoft-Windows-Shell-Setup-OOBE-NetworkLocation</a></p></td>
<td><p>This is not applicable for Windows 10.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-visualeffects-systemdefaultbackgroundcolor.md" data-raw-source="[Microsoft-Windows-Shell-Setup-VisualEffects-SystemDefaultBackgroundColor](microsoft-windows-shell-setup-visualeffects-systemdefaultbackgroundcolor.md)">Microsoft-Windows-Shell-Setup-VisualEffects-SystemDefaultBackgroundColor</a></p></td>
<td><p>This setting is deprecated in Windows 10 and should not be used. The default background color during OOBE is always dark. To align with this change, partners can no longer change the default screen background color during OOBE.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-helpandsupport-helpandsupport.md" data-raw-source="[Microsoft-Windows-HelpAndSupport-HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md)">Microsoft-Windows-HelpAndSupport-HelpAndSupport</a></p></td>
<td><p>In Windows 10, the <a href="microsoft-windows-helpandsupport-helpandsupport.md" data-raw-source="[HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md)">HelpAndSupport</a> settings are deprecated because the Help component that they impact is being retired. Existing information about the HelpAndSupport settings are provided for reference only.</p>
<p>In Windows 10, the OS disables the help components that shipped in Windows 8 and Windows 8.1 including the Help and Support Windows desktop application (HelpPane.exe). HelpPane.exe will continue to exist in the box, but calls to its interfaces will result in one of two outcomes:</p>
<ul>
<li>If the user is offline, the OS launches the Getting Started app.</li>
<li>If the user is online, the OS opens a browser instance and redirects the browser to an online topic.</li>
</ul>
<p>For more information on how OEMs can include their customer support contact information in the Contact Support App or Support Web page, see <a href="microsoft-windows-shell-setup-oeminformation.md" data-raw-source="[OEMInformation](microsoft-windows-shell-setup-oeminformation.md)">OEMInformation</a>.</p></td>
</tr>
</tbody>
</table>

### <a href="" id="removedsettings"></a>Removed Windows settings

The following components and/or settings are no longer available in Windows 10:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Removed setting from Windows 8.1 or Windows Server 2012 R2</th>
<th>Recommendation for Windows 10 for desktop editions</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft-Windows-Store-Client-UI\StoreContentModifier</p></td>
<td><p>The component and setting have been removed.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-MigrationWizardApplication\HideDiscontinuedComponents</p></td>
<td><p>The component and setting have been removed.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-ehome-reg-inf component and settings</p></td>
<td><p>Windows Media Center is no longer supported as of Windows 10. The component and settings have been removed.</p></td>
</tr>
</tbody>
</table>

### <a href="" id="removediesettings"></a>Removed Internet Explorer settings

These settings in the Microsoft-Windows-IE-InternetExplorer component are removed:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Deprecated setting name</th>
<th>Status or recommendation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft-Windows-IE-InternetExplorer\SearchScopes\Scope\ShowTopResult</p></td>
<td><p>The setting has been removed.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-IE-InternetExplorer\SearchScopes\Scope\TopResultURL</p></td>
<td><p>The setting has been removed.</p></td>
</tr>
</tbody>
</table>

## Changed answer file settings for Windows 8.1 and Windows Server 2012 R2

The table below describes Windows 8.1 and Windows Server 2012 R2 answer-file settings that have changed since Windows 8 and Windows Server 2012.

### <a href="" id="newwindowssettings"></a>New Windows Settings

These settings are new in Windows 8.1 Update, Windows 8.1 and Windows Server 2012 R2:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>New setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="microsoft-windows-coremmres-camerasoundlevel.md" data-raw-source="[Microsoft-Windows-CoreMmRes-CameraSoundLevel](microsoft-windows-coremmres-camerasoundlevel.md)">Microsoft-Windows-CoreMmRes-CameraSoundLevel</a></p></td>
<td><p>Sets the volume of the sound played when a user starts a recording, stops a recording, takes a photo or starts a photo sequence. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-coremmres-nophysicalcameraled.md" data-raw-source="[Microsoft-Windows-CoreMmRes-NoPhysicalCameraLED](microsoft-windows-coremmres-nophysicalcameraled.md)">Microsoft-Windows-CoreMmRes-NoPhysicalCameraLED</a></p></td>
<td><p>Indicates that there is no physical LED for the device’s camera. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-gpiobuttons-convertibleslatemode.md" data-raw-source="[Microsoft-Windows-GPIOButtons-ConvertibleSlateMode](microsoft-windows-gpiobuttons-convertibleslatemode.md)">Microsoft-Windows-GPIOButtons-ConvertibleSlateMode</a></p></td>
<td><p>Sets the touchscreen behavior for a laptop, a PC with permanently attached keyboard available at any time for typing comfortably</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-securestartup-filterdriver-preventdeviceencryption.md" data-raw-source="[Microsoft-Windows-SecureStartup-FilterDriver-PreventDeviceEncryption](microsoft-windows-securestartup-filterdriver-preventdeviceencryption.md)">Microsoft-Windows-SecureStartup-FilterDriver-PreventDeviceEncryption</a></p></td>
<td><p>Prevents encrypting the operating system drive and any fixed data drive using Windows BitLocker Drive Encryption.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-desktopoptimization.md" data-raw-source="[Microsoft-Windows-Shell-Setup-DesktopOptimization](microsoft-windows-shell-setup-desktopoptimization.md)">Microsoft-Windows-Shell-Setup-DesktopOptimization</a></p></td>
<td><p>Specifies display settings that affect the desktop. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-showpowerbuttononstartscreen.md" data-raw-source="[Microsoft-Windows-Shell-Setup-ShowPowerButtonOnStartScreen](microsoft-windows-shell-setup-showpowerbuttononstartscreen.md)">Microsoft-Windows-Shell-Setup-ShowPowerButtonOnStartScreen</a></p></td>
<td><p>Specifies that the Power Options button is displayed on the Start Screen. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile7.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile7](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile7.md)">Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile7</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> screen, in position SquareOrDesktopTile7. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile8.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile8](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile8.md)">Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile8</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> screen, in position SquareOrDesktopTile8. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile9.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile9](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile9.md)">Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile9</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> screen, in position SquareOrDesktopTile9. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile10.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile10](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile10.md)">Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile10</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> screen, in position SquareOrDesktopTile10. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile11.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile11](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile11.md)">Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile11</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> screen, in position SquareOrDesktopTile11. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile12.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile12](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile12.md)">Microsoft-Windows-Shell-Setup-StartTiles-SquareTiles-SquareOrDesktopTile12</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> screen, in position SquareOrDesktopTile12. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-systemsettings-displaynetworkselection.md" data-raw-source="[Microsoft-Windows-SystemSettings-DisplayNetworkSelection](microsoft-windows-systemsettings-displaynetworkselection.md)">Microsoft-Windows-SystemSettings-DisplayNetworkSelection</a></p></td>
<td><p>Specifies whether to always show the Network Selection control in the <strong>Mobile Broadband Properties</strong> dialog.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-systemsettings-wifitowlan.md" data-raw-source="[Microsoft-Windows-SystemSettings-WiFiToWlan](microsoft-windows-systemsettings-wifitowlan.md)">Microsoft-Windows-SystemSettings-WiFiToWlan</a></p></td>
<td><p>Replaces the. &quot;Wi-Fi&quot; heading in the Networks list with &quot;WLAN&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-wwanui-notinoobe.md" data-raw-source="[Microsoft-Windows-WWANUI-NotInOOBE](microsoft-windows-wwanui-notinoobe.md)">Microsoft-Windows-WWANUI-NotInOOBE</a></p></td>
<td><p>Hides mobile broadband devices and networks in OOBE.</p></td>
</tr>
<tr class="even">
<td><p><a href="security-malware-windows-defender-definitionupdatefilesharessources.md" data-raw-source="[Security-Malware-Windows-Defender-DefinitionUpdateFileSharesSources](security-malware-windows-defender-definitionupdatefilesharessources.md)">Security-Malware-Windows-Defender-DefinitionUpdateFileSharesSources</a></p></td>
<td><p>Configures UNC file share sources for downloading definition updates for Windows Defender.</p></td>
</tr>
<tr class="odd">
<td><p><a href="security-malware-windows-defender-enableremotemanageddefaults.md" data-raw-source="[Security-Malware-Windows-Defender-EnableRemoteManagedDefaults](security-malware-windows-defender-enableremotemanageddefaults.md)">Security-Malware-Windows-Defender-EnableRemoteManagedDefaults</a></p></td>
<td><p>Specifies whether to configure Windows Defender to be remotely managed using recommended default settings.</p></td>
</tr>
<tr class="even">
<td><p><a href="security-malware-windows-defender-fallbackorder.md" data-raw-source="[Security-Malware-Windows-Defender-FallbackOrder](security-malware-windows-defender-fallbackorder.md)">Security-Malware-Windows-Defender-FallbackOrder</a></p></td>
<td><p>Specifies the order in which different definition update sources should be contacted by Windows Defender.</p></td>
</tr>
<tr class="odd">
<td><p><a href="security-malware-windows-defender-scan.md" data-raw-source="[Security-Malware-Windows-Defender-Scan](security-malware-windows-defender-scan.md)">Security-Malware-Windows-Defender-Scan</a></p></td>
<td><p>Specifies settings that configure the scheduled scan for Windows Defender.</p></td>
</tr>
<tr class="even">
<td><p><a href="security-malware-windows-defender-signatureupdateinterval.md" data-raw-source="[Security-Malware-Windows-Defender-SignatureUpdateInterval](security-malware-windows-defender-signatureupdateinterval.md)">Security-Malware-Windows-Defender-SignatureUpdateInterval</a></p></td>
<td><p>Specifies the interval Windows Defender checks for definition updates.</p></td>
</tr>
<tr class="odd">
<td><p><a href="security-malware-windows-defender-threatseveritydefaultaction.md" data-raw-source="[Security-Malware-Windows-Defender-ThreatSeverityDefaultAction](security-malware-windows-defender-threatseveritydefaultaction.md)">Security-Malware-Windows-Defender-ThreatSeverityDefaultAction</a></p></td>
<td><p>Specifies settings that define the default action to be taken for specific threat alert levels.</p></td>
</tr>
</tbody>
</table>

### <a href="" id="changedwindowssettings"></a>Changed Windows Settings

These Windows 8.1 and Windows Server 2012 R2 settings have changed from Windows 8 and Windows Server 2012:

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Changed setting</th>
<th>Description of setting</th>
<th>Description of change</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-order.md" data-raw-source="[Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOverride-Order](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-order.md)">Microsoft-Windows-Shell-Setup-StartTiles-RegionalOverrides-RegionalOverride-Order</a></p></td>
<td><p>Specifies a unique id for a set of regions. In the specified set of regions, Windows displays a customized set of apps that appear on the Start and Lock screens.</p></td>
<td><p>Changed the maximum value of unique IDs for the regional override from 19 to 199.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-visualeffects-systemdefaultbackgroundcolor.md" data-raw-source="[Microsoft-Windows-Shell-Setup-VisualEffects-SystemDefaultBackgroundColor](microsoft-windows-shell-setup-visualeffects-systemdefaultbackgroundcolor.md)">Microsoft-Windows-Shell-Setup-VisualEffects-SystemDefaultBackgroundColor</a></p></td>
<td><p>Specifies the system default Windows background color scheme appearing on first boot, and on LogonUI if no user is selected.</p></td>
<td><p>Added new color scheme for Windows 8.1.</p></td>
</tr>
<tr class="odd">
<td><p>Networking-MPSSVC-Svc: <a href="networking-mpssvc-svcdomainprofile-disablenotifications.md" data-raw-source="[DomainProfile_DisableNotifications](networking-mpssvc-svcdomainprofile-disablenotifications.md)">DomainProfile_DisableNotifications</a>, <a href="networking-mpssvc-svcprivateprofile-disablenotifications.md" data-raw-source="[PrivateProfile_DisableNotifications](networking-mpssvc-svcprivateprofile-disablenotifications.md)">PrivateProfile_DisableNotifications</a>, and <a href="networking-mpssvc-svcpublicprofile-disablenotifications.md" data-raw-source="[PublicProfile_DisableNotifications](networking-mpssvc-svcpublicprofile-disablenotifications.md)">PublicProfile_DisableNotifications</a>.</p></td>
<td><p>Multiple settings</p></td>
<td><p>Changed default value for Windows RT 8.1.</p></td>
</tr>
</tbody>
</table>

### <a href="" id="renamedordeprecatedsettings"></a>Deprecated Windows Settings

The following Windows 8 and Windows Server 2012 settings are not supported in Windows 8.1 and Windows Server 2012 R2, and may be removed in a future release. The following table includes status of the setting, and recommendations for new settings to use when applicable:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Deprecated setting from Windows 8 or Windows Server 2012</th>
<th>Status or recommendation for Windows 8.1 or Windows Server 2012 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>microsoft-windows-mobilepc-sensors-api-\SensorPermissions\Sensor\Enable</p></td>
<td><p>This is not applicable for Windows 8.1.</p></td>
</tr>
<tr class="even">
<td><p>microsoft-windows-mobilepc-sensors-api-\SensorPermissions\Sensor\GUID</p></td>
<td><p>This is not applicable for Windows 8.1.</p></td>
</tr>
<tr class="odd">
<td><p>microsoft-windows-mobilepc-sensors-api-\SensorPermissions\Sensor\GUIDClassification</p></td>
<td><p>This is not applicable for Windows 8.1.</p></td>
</tr>
<tr class="even">
<td><p>microsoft-windows-mobilepc-sensors-api-\SensorPermissions\Sensor\Order</p></td>
<td><p>This is not applicable for Windows 8.1.</p></td>
</tr>
<tr class="odd">
<td><p>microsoft-windows-securestartup-filterdriver-\InPlaceCrypto</p></td>
<td><p>This is not applicable for Windows 8.1.</p></td>
</tr>
<tr class="even">
<td><p>microsoft-windows-securestartup-filterdriver-\ModifiedWriteMaximum</p></td>
<td><p>This is not applicable for Windows 8.1.</p></td>
</tr>
<tr class="odd">
<td><p>microsoft-windows-securestartup-filterdriver- \ReadDoubleBuffering</p></td>
<td><p>This is not applicable for Windows 8.1.</p></td>
</tr>
</tbody>
</table>

### <a href="" id="deprecatediesettings"></a>Deprecated Internet Explorer Settings

These settings in the Microsoft-Windows-IE-InternetExplorer component are deprecated:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Deprecated setting name</th>
<th>Status or recommendation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft-Windows-IE-InternetExplorer\AllSitesCompatibilityMode</p></td>
<td><p>This setting is not supported.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-IE-InternetExplorer\DisableWelcomePage</p></td>
<td><p>This setting was deprecated in Windows 8 and is no longer supported.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-IE-InternetExplorer\NoDial</p></td>
<td><p>Internet Explorer 9 through Internet Explorer 11 do not include an IEAK-based sign-up process.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-ie-internetexplorer-preapprovedaddons.md" data-raw-source="[Microsoft-Windows-IE-InternetExplorer-PreApprovedAddons](microsoft-windows-ie-internetexplorer-preapprovedaddons.md)">Microsoft-Windows-IE-InternetExplorer-PreApprovedAddons</a></p></td>
<td><p>Add-ons can still be installed but they will be disabled, by default. Users will be able to choose the add-ons to enable.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-IE-InternetExplorer\ShowCompatibilityViewButton</p></td>
<td><p>This setting is not supported.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-IE-InternetExplorer\SmallCommandBarIcons</p></td>
<td><p>This setting is not supported.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-IE-InternetExplorer\Scope\DisplayQuickPick</p></td>
<td><p>This setting is not supported.</p></td>
</tr>
</tbody>
</table>

### <a href="" id="removedsettings"></a>Removed Windows Settings

We recommend these replacements for Windows 8 and Windows Server 2012 settings that have been removed from Windows 8 and Windows Server 2012:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Removed setting from Windows 8 or Windows Server 2012</th>
<th>Recommendation for Windows 8.1 or Windows Server 2012 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft-Windows-PerfCenterCPL\WindowsExperienceIndexOemInfo\HardwareUpgradeURL</p></td>
<td><p>No recommendation.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-PerfCenterCPL\WindowsExperienceIndexOemInfo\Logo</p></td>
<td><p>No recommendation.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-AllUserInstallAgent\LogonWaitForPackageRegistration</p></td>
<td><p>No recommendation.</p></td>
</tr>
</tbody>
</table>

### <a href="" id="removediesettings"></a>Removed Internet Explorer Settings

These settings in the Microsoft-Windows-IE-InternetExplorer component are removed:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Deprecated setting name</th>
<th>Status or recommendation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft-Windows-IE-InternetExplorer: EnableLinksBar, ShowCommandBar, ShowMenuBar, and ShowStatusBar.</p></td>
<td><p>Users can still make these bars appear in Internet Explorer for the desktop.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-IE-InternetExplorer\IEWelcomeMsg</p></td>
<td><p>To skip the First Run wizard and the welcome page when Internet Explorer starts for the first time, use the <a href="microsoft-windows-ie-internetexplorer-disablefirstrunwizard.md" data-raw-source="[DisableFirstRunWizard](microsoft-windows-ie-internetexplorer-disablefirstrunwizard.md)">DisableFirstRunWizard</a> settings.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-IE-InternetExplorer\PrintBackground</p></td>
<td><p>This setting is not supported.</p></td>
</tr>
</tbody>
</table>
