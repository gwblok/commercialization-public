---
title: Changed answer file settings for Windows 8.1 and Windows Server 2012 R2
description: This topic describes Windows 8.1 and Windows Server 2012 R2 answer-file settings that have changed since Windows 8 and Windows Server 2012.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6b64c934-6be0-4897-be89-041bf86e46f9
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article
redirect_url: https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/unattend/changed-answer-file-settings-for-previous-windows10-builds
---

# Changed answer file settings for Windows 8.1 and Windows Server 2012 R2


This topic describes Windows 8.1 and Windows Server 2012 R2 answer-file settings that have changed since Windows 8 and Windows Server 2012.

## In This Section


-   [New Windows Settings](#newwindowssettings)

-   [Changed Windows Settings](#changedwindowssettings)

-   [Deprecated Windows Settings](#renamedordeprecatedsettings)

-   [Deprecated Internet Explorer Settings](#deprecatediesettings)

-   [Removed Windows Settings](#removedsettings)

-   [Removed Internet Explorer Settings](#removediesettings)

## <a href="" id="newwindowssettings"></a>New Windows Settings


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
<td><p>Microsoft-Windows-CoreMmRes<a href="microsoft-windows-coremmres-camerasoundlevel.md" data-raw-source="[CameraSoundLevel](microsoft-windows-coremmres-camerasoundlevel.md)">CameraSoundLevel</a></p></td>
<td><p>Sets the volume of the sound played when a user starts a recording, stops a recording, takes a photo or starts a photo sequence. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-CoreMmRes<a href="microsoft-windows-coremmres-nophysicalcameraled.md" data-raw-source="[NoPhysicalCameraLED](microsoft-windows-coremmres-nophysicalcameraled.md)">NoPhysicalCameraLED</a></p></td>
<td><p>Indicates that there is no physical LED for the device’s camera. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-GPIOButtons<a href="microsoft-windows-gpiobuttons-convertibleslatemode.md" data-raw-source="[ConvertibleSlateMode](microsoft-windows-gpiobuttons-convertibleslatemode.md)">ConvertibleSlateMode</a></p></td>
<td><p>Sets the touchscreen behavior for a laptop, a PC with permanently attached keyboard available at any time for typing comfortably</p></td>
</tr>
<tr class="even">
<td><p>microsoft-windows-securestartup-filterdriver-<a href="microsoft-windows-securestartup-filterdriver-preventdeviceencryption.md" data-raw-source="[PreventDeviceEncryption](microsoft-windows-securestartup-filterdriver-preventdeviceencryption.md)">PreventDeviceEncryption</a></p></td>
<td><p>Prevents encrypting the operating system drive and any fixed data drive using Windows BitLocker Drive Encryption.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-Shell-Setup<a href="microsoft-windows-shell-setup-desktopoptimization.md" data-raw-source="[DesktopOptimization](microsoft-windows-shell-setup-desktopoptimization.md)">DesktopOptimization</a></p></td>
<td><p>Specifies display settings that affect the desktop. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-Shell-Setup <a href="microsoft-windows-shell-setup-showpowerbuttononstartscreen.md" data-raw-source="[ShowPowerButtonOnStartScreen](microsoft-windows-shell-setup-showpowerbuttononstartscreen.md)">ShowPowerButtonOnStartScreen</a></p></td>
<td><p>Specifies that the Power Options button is displayed on the Start Screen. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-Shell-Setup\StartTiles\SquareTiles<a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile7.md" data-raw-source="[SquareOrDesktopTile7](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile7.md)">SquareOrDesktopTile7</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> screen, in position SquareOrDesktopTile7. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-Shell-Setup\StartTiles\SquareTiles<a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile8.md" data-raw-source="[SquareOrDesktopTile8](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile8.md)">SquareOrDesktopTile8</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> screen, in position SquareOrDesktopTile8. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-Shell-Setup\StartTiles\SquareTiles<a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile9.md" data-raw-source="[SquareOrDesktopTile9](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile9.md)">SquareOrDesktopTile9</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> screen, in position SquareOrDesktopTile9. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-Shell-Setup\StartTiles\SquareTiles<a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile10.md" data-raw-source="[SquareOrDesktopTile10](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile10.md)">SquareOrDesktopTile10</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> screen, in position SquareOrDesktopTile10. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-Shell-Setup\StartTiles\SquareTiles<a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile11.md" data-raw-source="[SquareOrDesktopTile11](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile11.md)">SquareOrDesktopTile11</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> screen, in position SquareOrDesktopTile11. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-Shell-Setup\StartTiles\SquareTiles<a href="microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile12.md" data-raw-source="[SquareOrDesktopTile12](microsoft-windows-shell-setup-starttiles-squaretiles-squareordesktoptile12.md)">SquareOrDesktopTile12</a></p></td>
<td><p>Specifies which application appears as a square tile on the <strong>Start</strong> screen, in position SquareOrDesktopTile12. New for Windows 8.1 Update.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-SystemSettings<a href="microsoft-windows-systemsettingsthreshold-displaynetworkselection.md" data-raw-source="[DisplayNetworkSelection](microsoft-windows-systemsettingsthreshold-displaynetworkselection.md)">DisplayNetworkSelection</a></p></td>
<td><p>Specifies whether to always show the Network Selection control in the <strong>Mobile Broadband Properties</strong> dialog.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-SystemSettings<a href="microsoft-windows-systemsettings-wifitowlan.md" data-raw-source="[WiFiToWlan](microsoft-windows-systemsettings-wifitowlan.md)">WiFiToWlan</a></p></td>
<td><p>Replaces the. &quot;Wi-Fi&quot; heading in the Networks list with &quot;WLAN&quot;.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft-Windows-WwanUI<a href="microsoft-windows-wwanui-notinoobe.md" data-raw-source="[NotInOOBE](microsoft-windows-wwanui-notinoobe.md)">NotInOOBE</a></p></td>
<td><p>Hides mobile broadband devices and networks in OOBE.</p></td>
</tr>
<tr class="even">
<td><p>Security-Malware-Windows-Defender<a href="security-malware-windows-defender-definitionupdatefilesharessources.md" data-raw-source="[DefinitionUpdateFileSharesSources](security-malware-windows-defender-definitionupdatefilesharessources.md)">DefinitionUpdateFileSharesSources</a></p></td>
<td><p>Configures UNC file share sources for downloading definition updates for Windows Defender.</p></td>
</tr>
<tr class="odd">
<td><p>Security-Malware-Windows-Defender<a href="security-malware-windows-defender-enableremotemanageddefaults.md" data-raw-source="[EnableRemoteManagedDefaults](security-malware-windows-defender-enableremotemanageddefaults.md)">EnableRemoteManagedDefaults</a></p></td>
<td><p>Specifies whether to configure Windows Defender to be remotely managed using recommended default settings.</p></td>
</tr>
<tr class="even">
<td><p>Security-Malware-Windows-Defender<a href="security-malware-windows-defender-fallbackorder.md" data-raw-source="[FallbackOrder](security-malware-windows-defender-fallbackorder.md)">FallbackOrder</a></p></td>
<td><p>Specifies the order in which different definition update sources should be contacted by Windows Defender.</p></td>
</tr>
<tr class="odd">
<td><p>Security-Malware-Windows-Defender<a href="security-malware-windows-defender-scan.md" data-raw-source="[Scan](security-malware-windows-defender-scan.md)">Scan</a></p></td>
<td><p>Specifies settings that configure the scheduled scan for Windows Defender.</p></td>
</tr>
<tr class="even">
<td><p>Security-Malware-Windows-Defender<a href="security-malware-windows-defender-signatureupdateinterval.md" data-raw-source="[SignatureUpdateInterval](security-malware-windows-defender-signatureupdateinterval.md)">SignatureUpdateInterval</a></p></td>
<td><p>Specifies the interval Windows Defender checks for definition updates.</p></td>
</tr>
<tr class="odd">
<td><p>Security-Malware-Windows-Defender<a href="security-malware-windows-defender-threatseveritydefaultaction.md" data-raw-source="[ThreatSeverityDefaultAction](security-malware-windows-defender-threatseveritydefaultaction.md)">ThreatSeverityDefaultAction</a></p></td>
<td><p>Specifies settings that define the default action to be taken for specific threat alert levels.</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="changedwindowssettings"></a>Changed Windows Settings


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
<td><p>Microsoft-Windows-Shell-Setup\StartTiles\RegionalOverrides\RegionalOverride<a href="microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-order.md" data-raw-source="[Order](microsoft-windows-shell-setup-starttiles-regionaloverrides-regionaloverride-order.md)">Order</a></p></td>
<td><p>Specifies a unique id for a set of regions. In the specified set of regions, Windows displays a customized set of apps that appear on the Start and Lock screens.</p></td>
<td><p>Changed the maximum value of unique IDs for the regional override from 19 to 199.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-Shell-Setup\VisualEffects<a href="microsoft-windows-shell-setup-visualeffects-systemdefaultbackgroundcolor.md" data-raw-source="[SystemDefaultBackgroundColor](microsoft-windows-shell-setup-visualeffects-systemdefaultbackgroundcolor.md)">SystemDefaultBackgroundColor</a></p></td>
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

 

## <a href="" id="renamedordeprecatedsettings"></a>Deprecated Windows Settings


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

 

## <a href="" id="deprecatediesettings"></a>Deprecated Internet Explorer Settings


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
<td><p>Microsoft-Windows-IE-InternetExplorer<a href="microsoft-windows-ie-internetexplorer-preapprovedaddons.md" data-raw-source="[PreApprovedAddons](microsoft-windows-ie-internetexplorer-preapprovedaddons.md)">PreApprovedAddons</a></p></td>
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

 

## <a href="" id="removedsettings"></a>Removed Windows Settings


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

 

## <a href="" id="removediesettings"></a>Removed Internet Explorer Settings


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








