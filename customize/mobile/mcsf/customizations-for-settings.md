---
title: Customizations for Settings
description: The Settings app contains a predefined collection of user-configurable system settings that's organized into pages by functionality.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c25e8fc8-09aa-4d3d-8288-26de2f43332b


ms.date: 05/02/2017
ms.topic: article


redirect_url: https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/managed-centralized-settings-framework-mcsf
---

# Customizations for Settings


The **Settings** app contains a predefined collection of user-configurable system settings that's organized into pages by functionality. As specified in policy, the appearance and default values of these settings are generally not customizable. The following table contain the complete list of user-facing settings that OEMs and mobile operators can change.

## In this section


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Topic</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/library/windows/hardware/mt762907" data-raw-source="[Start + theme settings: Enabling dark mode](https://msdn.microsoft.com/library/windows/hardware/mt762907)">Start + theme settings: Enabling dark mode</a></p></td>
<td><p>OEMs can choose to specify whether the dark mode is applied.</p></td>
</tr>
<tr class="even">
<td><p><a href="warning-about-light-theme-for-amoled-and-oled-screens.md" data-raw-source="[Start + theme settings: Warning about light theme for AMOLED and OLED screens](warning-about-light-theme-for-amoled-and-oled-screens.md)">Start + theme settings: Warning about light theme for AMOLED and OLED screens</a></p></td>
<td><p>OEMs can choose to display a warning about battery life if the user selects the light theme on phones with AMOLED or OLED displays.</p></td>
</tr>
<tr class="odd">
<td><p><a href="additional-alarms.md" data-raw-source="[Ringtones + sounds settings: Additional alarms](additional-alarms.md)">Ringtones + sounds settings: Additional alarms</a></p></td>
<td><p>Partners can add one additional alarm sound to the phone for use in the <strong>Alarm &amp; Clocks</strong> app. Partners can also set a new default alarm.</p></td>
</tr>
<tr class="even">
<td><p><a href="additional-notification-sounds.md" data-raw-source="[Ringtones + sounds settings: Additional notification sounds](additional-notification-sounds.md)">Ringtones + sounds settings: Additional notification sounds</a></p></td>
<td><p>Partners can add up to three new notification sounds and a reminder sound. In addition, you can also specify a default notification sound for messaging, voicemails, and reminders.</p></td>
</tr>
<tr class="odd">
<td><p><a href="additional-ringtones.md" data-raw-source="[Ringtones + sounds settings: Additional ringtones](additional-ringtones.md)">Ringtones + sounds settings: Additional ringtones</a></p></td>
<td><p>OEMs and mobile operators can each preload a set of custom ringtone files on Windows mobile devices, and they can set a default ringtone.</p></td>
</tr>
<tr class="even">
<td><p><a href="call-drop-and-call-waiting-sounds.md" data-raw-source="[Ringtones + sounds settings: Call drop and call waiting sounds](call-drop-and-call-waiting-sounds.md)">Ringtones + sounds settings: Call drop and call waiting sounds</a></p></td>
<td><p>OEMs can customize the call drop and call waiting sounds.</p></td>
</tr>
<tr class="odd">
<td><p><a href="camera-shutter-sound.md" data-raw-source="[Ringtones + sounds settings: Camera shutter sound](camera-shutter-sound.md)">Ringtones + sounds settings: Camera shutter sound</a></p></td>
<td><p>The camera shutter sound that occurs when the user takes a picture or starts filming a video can be turned off by removing the <strong>Camera shutter</strong> option from the <strong>Sounds</strong> settings screen.</p></td>
</tr>
<tr class="even">
<td><p><a href="ringtone-store-application.md" data-raw-source="[Ringtones + sounds settings: Ringtone store application](ringtone-store-application.md)">Ringtones + sounds settings: Ringtone store application</a></p></td>
<td><p>Partner apps can be used to sell ringtones to users. The app owner must provide the service for the ringtone catalog and to manage downloads. Users are shown an option to <strong>Get more</strong> ringtones in the ringtone picker, from which they can automatically launch the ringtone store application.</p></td>
</tr>
<tr class="odd">
<td><p><a href="additional-lock-screen-backgrounds.md" data-raw-source="[Lock screen settings: Additional lock screen backgrounds](additional-lock-screen-backgrounds.md)">Lock screen settings: Additional lock screen backgrounds</a></p></td>
<td><p>OEMs can add new lock screen background images for the lock screen and also set the default lock screen background.</p></td>
</tr>
<tr class="even">
<td><p><a href="lock-screen-notifications.md" data-raw-source="[Lock screen settings: Lock screen notifications](lock-screen-notifications.md)">Lock screen settings: Lock screen notifications</a></p></td>
<td><p>OEMs can preload apps that support lock screen notifications.</p></td>
</tr>
<tr class="odd">
<td><p><a href="screen-time-out-for-amoled-and-oled-displays.md" data-raw-source="[Lock screen settings: Screen timeout for AMOLED and OLED displays](screen-time-out-for-amoled-and-oled-displays.md)">Lock screen settings: Screen timeout for AMOLED and OLED displays</a></p></td>
<td><p>OEMs can remove the <strong>15 minutes</strong>, <strong>30 minutes</strong>, and <strong>Never</strong> options from the <strong>Screen times out after</strong> dropdown in the <strong>Lock screen</strong> settings screen.</p>
<p>This is recommended for phones with AMOLED and OLED screens to prevent screen damage.</p></td>
</tr>
<tr class="even">
<td><p><a href="configure-quick-settings.md" data-raw-source="[Notifications + actions settings: Configure Quick actions](configure-quick-settings.md)">Notifications + actions settings: Configure Quick actions</a></p></td>
<td><p>OEMs can change the default set of actions for each slot on the <strong>Quick actions</strong> screen in <strong>Notifications &amp; actions</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><a href="change-wi-fi-to-wlan.md" data-raw-source="[Wi-Fi settings: Change Wi-Fi to WLAN](change-wi-fi-to-wlan.md)">Wi-Fi settings: Change Wi-Fi to WLAN</a></p></td>
<td><p>To meet regulatory requirements and/or meet mobile operator requirements for some markets, partners can replace the string <strong>Wi-Fi</strong> with the generic term <strong>WLAN</strong>.</p></td>
</tr>
<tr class="even">
<td><p><a href="enable-static-ip.md" data-raw-source="[Wi-Fi settings: Enable static IP](enable-static-ip.md)">Wi-Fi settings: Enable static IP</a></p></td>
<td><p>To facilitate Wi-Fi certification tests, OEMs can enable a screen from the Wi-Fi settings screen that provides UI elements that allow you to specify a static IP address, gateway address, and DNS server address.</p></td>
</tr>
<tr class="odd">
<td><p><a href="limited-connectivity-status.md" data-raw-source="[Wi-Fi settings: Limited connectivity status](limited-connectivity-status.md)">Wi-Fi settings: Limited connectivity status</a></p></td>
<td><p>Partners may override the default status message shown when a device is connected to a Wi-Fi access point.</p></td>
</tr>
<tr class="even">
<td><p><a href="wi-fi-always-on-always-connected.md" data-raw-source="[Wi-Fi settings: Wi-Fi always on, always connected](wi-fi-always-on-always-connected.md)">Wi-Fi settings: Wi-Fi always on, always connected</a></p></td>
<td><p>Partners can modify AOAC behavior and UX for non-AOAC mode devices.</p></td>
</tr>
<tr class="odd">
<td><p><a href="wi-fi-icon-and-notifications.md" data-raw-source="[Wi-Fi settings: Wi-Fi icon and notifications](wi-fi-icon-and-notifications.md)">Wi-Fi settings: Wi-Fi icon and notifications</a></p></td>
<td><p>Partners can configure settings related to the Wi-Fi icon.</p></td>
</tr>
<tr class="even">
<td><p><a href="add-a-suffix-to-the-mobile-operator-name.md" data-raw-source="[Cellular + SIM settings: Add a suffix to the mobile operator name](add-a-suffix-to-the-mobile-operator-name.md)">Cellular + SIM settings: Add a suffix to the mobile operator name</a></p></td>
<td><p>To meet branding requirements for some mobile operators, OEMs can add a suffix to the network name that is displayed on the phone.</p></td>
</tr>
<tr class="odd">
<td><p><a href="additional-internet-apn-settings.md" data-raw-source="[Cellular + SIM settings: Additional Internet APN settings](additional-internet-apn-settings.md)">Cellular + SIM settings: Additional Internet APN settings</a></p></td>
<td><p>OEMs can hide both the <strong>add internet apn</strong> button and the <strong>IP type</strong> listbox in the <strong>internet APN</strong> settings screen.</p></td>
</tr>
<tr class="even">
<td><p><a href="background-cellular-data-restriction.md" data-raw-source="[Cellular + SIM settings: Background cellular data restriction](background-cellular-data-restriction.md)">Cellular + SIM settings: Background cellular data restriction</a></p></td>
<td><p>To meet market or mobile operator requirements, OEMs can restrict background data in the data usage settings.</p></td>
</tr>
<tr class="odd">
<td><p><a href="cellular-data-fallback-when-in-limited-wi-fi-connectivity.md" data-raw-source="[Cellular + SIM settings: Cellular data fallback when in limited Wi-Fi connectivity](cellular-data-fallback-when-in-limited-wi-fi-connectivity.md)">Cellular + SIM settings: Cellular data fallback when in limited Wi-Fi connectivity</a></p></td>
<td><p>OEMs can change the default behavior for the device when Wi-Fi connectivity becomes limited.</p></td>
</tr>
<tr class="even">
<td><p><a href="cellular-settings-for-phones.md" data-raw-source="[Cellular + SIM settings: Cellular settings for phones](cellular-settings-for-phones.md)">Cellular + SIM settings: Cellular settings for phones</a></p></td>
<td><p>OEMs can hide certain user options for phones that appear in the <strong>Cellular &amp; SIM</strong> screen in <strong>Settings</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><a href="change-sim-to-simuim.md" data-raw-source="[Cellular + SIM settings: Change SIM to SIM/UIM](change-sim-to-simuim.md)">Cellular + SIM settings: Change SIM to SIM/UIM</a></p></td>
<td><p>Partners can change the string &quot;SIM&quot; to &quot;SIM/UIM&quot; in the device UI.</p></td>
</tr>
<tr class="even">
<td><p><a href="change-the-default-sim-name-to-match-the-spn-or-operator-name.md" data-raw-source="[Cellular + SIM settings: Change the default SIM name to match the SPN or operator name](change-the-default-sim-name-to-match-the-spn-or-operator-name.md)">Cellular + SIM settings: Change the default SIM name to match the SPN or operator name</a></p></td>
<td><p>By default, the OS displays <strong>SIM 1</strong> or <strong>SIM 2</strong> as the default friendly name for the SIM in slot 1 or slot 2 if the service provider name (SPN) or mobile operator name has not been set. Partners can use this customization to change the default name read from the SIM to define the SPN for SIM cards that do not contain this information or to generate the default friendly name for the SIM.</p></td>
</tr>
<tr class="odd">
<td><p><a href="connection-speed-option.md" data-raw-source="[Cellular + SIM settings: Connection speed option](connection-speed-option.md)">Cellular + SIM settings: Connection speed option</a></p></td>
<td><p>Partners can customize the listed names of the connection speeds, and can hide the user option to select the connection speed that is displayed on the <strong>SIM</strong> screen.</p></td>
</tr>
<tr class="even">
<td><p><a href="default-highest-connection-speed.md" data-raw-source="[Cellular + SIM settings: Default highest connection speed](default-highest-connection-speed.md)">Cellular + SIM settings: Default highest connection speed</a></p></td>
<td><p>Partners can set the default value for the <strong>Highest connection speed</strong> option in the <strong>Settings</strong> &gt; <strong>Cellular &amp; SIM</strong> &gt; <strong>SIM</strong> screen by specifying the bitmask for any combination of radio technology to be excluded from the default value. The connection speed that has not been excluded will show up as the highest connection speed.</p></td>
</tr>
<tr class="odd">
<td><p><a href="default-roaming-option.md" data-raw-source="[Cellular + SIM settings: Default roaming option](default-roaming-option.md)">Cellular + SIM settings: Default roaming option</a></p></td>
<td><p>Partners can set the default value for the <strong>Default roaming options</strong> option in the <strong>Cellular &amp; SIM</strong> settings screen.</p></td>
</tr>
<tr class="even">
<td><p><a href="extended-error-messages-for-reject-codes.md" data-raw-source="[Cellular + SIM settings: Extended error messages for reject codes](extended-error-messages-for-reject-codes.md)">Cellular + SIM settings: Extended error messages for reject codes</a></p></td>
<td><p>When a reject code is sent by the network, partners can specify that extended error messages should be displayed instead of the standard simple error messages.</p></td>
</tr>
<tr class="odd">
<td><p><a href="hide-cdma-mode-selection.md" data-raw-source="[Cellular + SIM settings: Hide CDMA mode selection](hide-cdma-mode-selection.md)">Cellular + SIM settings: Hide CDMA mode selection</a></p></td>
<td><p>For CDMA phones, partners can hide <strong>CDMA</strong> option in the network <strong>Mode</strong> selection drop-down that appears on the <strong>Cellular &amp; SIM</strong> screen in <strong>Settings</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><a href="manual-network-selection-timeout.md" data-raw-source="[Cellular + SIM settings: Manual network selection timeout](manual-network-selection-timeout.md)">Cellular + SIM settings: Manual network selection timeout</a></p></td>
<td><p>OEMs can change the default network selection timeout value.</p></td>
</tr>
<tr class="even">
<td><p><a href="permanent-automatic-mode.md" data-raw-source="[Cellular + SIM settings: Permanent automatic mode](permanent-automatic-mode.md)">Cellular + SIM settings: Permanent automatic mode</a></p></td>
<td><p>OEMs can enable permanent automatic mode for mobile networks that require the cellular settings to revert to automatic network selection after the user has manually selected another network when roaming or out of range of the home network.</p></td>
</tr>
<tr class="odd">
<td><p><a href="remove-the-trailing-msisdn-digits-on-a-sim-card.md" data-raw-source="[Cellular + SIM settings: Remove the trailing MSISDN digits on a SIM card](remove-the-trailing-msisdn-digits-on-a-sim-card.md)">Cellular + SIM settings: Remove the trailing MSISDN digits on a SIM card</a></p></td>
<td><p>OEMs can remove the trailing MSISDN digits from the service provider name (SPN) in the device UI.</p></td>
</tr>
<tr class="even">
<td><p><a href="settings-for-ims-services.md" data-raw-source="[Cellular + SIM settings: Settings for IMS services](settings-for-ims-services.md)">Cellular + SIM settings: Settings for IMS services</a></p></td>
<td><p>OEMs can configure the default settings and toggle for IMS services to meet mobile operator requirements.</p></td>
</tr>
<tr class="odd">
<td><p><a href="view-internet-apn.md" data-raw-source="[Cellular + SIM settings: View Internet APN](view-internet-apn.md)">Cellular + SIM settings: View Internet APN</a></p></td>
<td><p>For mobile operators that require it, OEMs can show the <strong>View Internet APN</strong> button in the <strong>Cellular &amp; SIM</strong> settings page for users that have a data plan.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/library/windows/hardware/mt651724" data-raw-source="[Cellular + SIM settings: Wi-Fi calling errors](https://msdn.microsoft.com/library/windows/hardware/mt651724)">Cellular + SIM settings: Wi-Fi calling errors</a></p></td>
<td><p>OEMs can customize the mobile device to configure settings related to Wi-Fi calling errors</p></td>
</tr>
<tr class="odd">
<td><p><a href="kids-corner-default-theme-and-accent-color.md" data-raw-source="[Kid&#39;s Corner: Default theme and accent color](kids-corner-default-theme-and-accent-color.md)">Kid&#39;s Corner: Default theme and accent color</a></p></td>
<td><p>Partners can set the default theme, including the background color (light or dark) and the accent color for Kid’s Corner.</p></td>
</tr>
<tr class="even">
<td><p><a href="brightness-tuning.md" data-raw-source="[Brightness settings: Brightness tuning](brightness-tuning.md)">Brightness settings: Brightness tuning</a></p></td>
<td><p>When the <strong>Brightness</strong> screen in <strong>Settings</strong> is not set to automatically adjust, this customization enables the user to select low, medium, and high intensities for the screen brightness.</p></td>
</tr>
<tr class="odd">
<td><p><a href="hide-the-auto-brightness-setting.md" data-raw-source="[Brightness settings: Hide the auto brightness setting](hide-the-auto-brightness-setting.md)">Brightness settings: Hide the auto brightness setting</a></p></td>
<td><p>OEMs can hide the automatic brightness setting for phones that do not have an ambient light sensor.</p></td>
</tr>
<tr class="even">
<td><p><a href="disabling-nitz-or-daylight-saving-time.md" data-raw-source="[Date + time settings: Disabling NITZ or daylight saving time](disabling-nitz-or-daylight-saving-time.md)">Date + time settings: Disabling NITZ or daylight saving time</a></p></td>
<td><p>OEMs can configure NITZ to handle daylight saving time appropriately for their market, or disable automatic setting of date and time completely.</p></td>
</tr>
<tr class="odd">
<td><p><a href="time-zone-priority-list.md" data-raw-source="[Date + time settings: Time zone priority list](time-zone-priority-list.md)">Date + time settings: Time zone priority list</a></p></td>
<td><p>Beginning with Windows 10 Mobile, this customization is no longer necessary as the OS supports a location-based timezone detection service. However, to maintain backwards compatibility for some RPAL APIs that were previously released (such as <strong>GetTimeZoneInformationID</strong>, <strong>SetTimeZoneInformationByID</strong>, and so on), an updated table of the timezone IDs is provided for your reference.</p></td>
</tr>
<tr class="even">
<td><p><a href="disabling-text-correction-and-suggestions.md" data-raw-source="[Keyboard settings: Disabling text correction and suggestions](disabling-text-correction-and-suggestions.md)">Keyboard settings: Disabling text correction and suggestions</a></p></td>
<td><p>For markets that do not use any of the available input languages, partners pick an alternative available input language as the default, but disable text prediction, auto-correction, and the spelling checker by default, using this customization.</p></td>
</tr>
<tr class="odd">
<td><p><a href="hardware-keyboard-character-repeats-hold-time-and-delay.md" data-raw-source="[Keyboard settings: Hardware keyboard character repeats hold time and delay](hardware-keyboard-character-repeats-hold-time-and-delay.md)">Keyboard settings: Hardware keyboard character repeats hold time and delay</a></p></td>
<td><p>For devices that have a hardware keyboard, partners can optionally set the character repeat hold time and delay.</p></td>
</tr>
<tr class="even">
<td><p><a href="pre-enabled-keyboard.md" data-raw-source="[Keyboard settings: Pre-enabled keyboard](pre-enabled-keyboard.md)">Keyboard settings: Pre-enabled keyboard</a></p></td>
<td><p>OEMs can use this customization to pre-enable additional device keyboards.</p></td>
</tr>
<tr class="odd">
<td><p><a href="text-correction-and-suggestions.md" data-raw-source="[Keyboard settings: Text correction and suggestions](text-correction-and-suggestions.md)">Keyboard settings: Text correction and suggestions</a></p></td>
<td><p>Partners must enable text correction and text suggestions for at least one input language, and can optionally include more.</p></td>
</tr>
<tr class="even">
<td><p><a href="phone-languages.md" data-raw-source="[Language settings: Mobile device languages](phone-languages.md)">Language settings: Mobile device languages</a></p></td>
<td><p>Partners must select the set of available languages to include on the mobile device. Partners must also specify one of the included languages as the default device language.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/library/windows/hardware/mt637405" data-raw-source="[Region settings: Default list of countries/regions](https://msdn.microsoft.com/library/windows/hardware/mt637405)">Region settings: Default list of countries/regions</a></p></td>
<td><p>OEMs can select the countries/regions to exclude from the default list shown in the mobile device&#39;s <strong>Country/Region</strong> list in the <strong>Settings</strong> screen.</p></td>
</tr>
<tr class="even">
<td><p><a href="regional-format.md" data-raw-source="[Region settings: Regional format](regional-format.md)">Region settings: Regional format</a></p></td>
<td><p>Partners can specify the default country/region, regional format, pre-enabled keyboard, and speech languages for the device.</p></td>
</tr>
<tr class="odd">
<td><p><a href="speech-languages.md" data-raw-source="[Speech settings: Speech languages](speech-languages.md)">Speech settings: Speech languages</a></p></td>
<td><p>OEMs can specify the speech languages to include on the mobile device.</p></td>
</tr>
<tr class="even">
<td><p><a href="telecoil-and-tty-support-for-accessibility.md" data-raw-source="[Ease of access settings: Telecoil and TTY support for accessibility](telecoil-and-tty-support-for-accessibility.md)">Ease of access settings: Telecoil and TTY support for accessibility</a></p></td>
<td><p>Partners can choose whether to show TTY and/or Telelcoil options in the device settings.</p></td>
</tr>
<tr class="odd">
<td><p><a href="auto-scan-for-phone-updates.md" data-raw-source="[Phone update settings: Auto scan for phone updates](auto-scan-for-phone-updates.md)">Phone update settings: Auto scan for phone updates</a></p></td>
<td><p>OEMs can show or hide the auto scan for updates setting on the device.</p></td>
</tr>
<tr class="even">
<td><p><a href="block-using-sd-card-for-updates.md" data-raw-source="[Phone update settings: Block using SD card for updates](block-using-sd-card-for-updates.md)">Phone update settings: Block using SD card for updates</a></p></td>
<td><p>For devices that support an SD card, OEMs can either allow or block the use of the SD card for device updates.</p></td>
</tr>
<tr class="odd">
<td><p><a href="enable-sd-card-override.md" data-raw-source="[Phone update settings: Enable SD card override](enable-sd-card-override.md)">Phone update settings: Enable SD card override</a></p></td>
<td><p>By default, using the SD card for device updates is disabled. OEMs who want to use the SD card for device updates must set <strong>EnableSDCardOverride</strong> to opt-in and re-enable updates using the SD card.</p></td>
</tr>
<tr class="even">
<td><p><a href="phone-metadata-in-devicetargetinginfo.md" data-raw-source="[About settings: Phone metadata in DeviceTargetingInfo](phone-metadata-in-devicetargetinginfo.md)">About settings: Phone metadata in DeviceTargetingInfo</a></p></td>
<td><p>Partners are required to set certain device metadata, including hardware, support, and OEM and MO information.</p></td>
</tr>
<tr class="odd">
<td><p><a href="fm-radio.md" data-raw-source="[FM Radio](fm-radio.md)">FM Radio</a></p></td>
<td><p>The BSP provided by the SoC vendor includes support for the FM radio.</p></td>
</tr>
<tr class="odd">
<td><p><a href="showing-the-fm-radio.md" data-raw-source="[Radio settings: Showing the FM radio](showing-the-fm-radio.md)">Radio settings: Showing the FM radio</a></p></td>
<td><p>For devices that include an FM radio chip, OEMs can show <strong>FM Radio</strong> in the Apps list.</p></td>
</tr>
<tr class="even">
<td><p><a href="fm-radio-frequency-band.md" data-raw-source="[Radio settings: FM radio frequency band](fm-radio-frequency-band.md)">Radio settings: FM radio frequency band</a></p></td>
<td><p>OEMs can change the default setting for the FM radio receiver to use an appropriate frequency for the market in which the device will be sold.</p></td>
</tr>
<tr class="odd">
<td><p><a href="default-value-for-browser-data-saver.md" data-raw-source="[Browser settings: Default value for browser data saver](default-value-for-browser-data-saver.md)">Browser settings: Default value for browser data saver</a></p></td>
<td><p>Partners can configure the default setting for the browser data saver feature by turning the browser optimization service on or off, using the <strong>BrowserDataSaver</strong> setting</p></td>
</tr>
<tr class="even">
<td><p><a href="show-pictures-automatically-when-browsing.md" data-raw-source="[Browser settings: Show pictures automatically when browsing](show-pictures-automatically-when-browsing.md)">Browser settings: Show pictures automatically when browsing</a></p></td>
<td><p>Partners can enable or disable the <strong>Show pictures automatically</strong> setting in the browser&#39;s <strong>advanced settings</strong> screen.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/library/windows/hardware/mt653694" data-raw-source="[Messaging settings: Adding an LED notification option](https://msdn.microsoft.com/library/windows/hardware/mt653694)">Messaging settings: Adding an LED notification option</a></p></td>
<td><p>OEMs can configure a registry key to specify a selected notification LED as the LED notification and then add an <strong>LED notification</strong> option to the device&#39;s messaging <strong>Settings</strong> screen.</p></td>
</tr>
<tr class="even">
<td><p><a href="cmas-required-monthly-test.md" data-raw-source="[Messaging settings: CMAS Required Monthly Test](cmas-required-monthly-test.md)">Messaging settings: CMAS Required Monthly Test</a></p></td>
<td><p>Windows supports the Commercial Mobile Alert System (CMAS) Required Monthly Test (RMT) messages. To enable this, OEMs can set a registry key so messages can be delivered to the device.</p></td>
</tr>
<tr class="odd">
<td><p><a href="disable-editing-of-the-sms-center-number.md" data-raw-source="[Messaging settings: Disable editing of the SMS center number](disable-editing-of-the-sms-center-number.md)">Messaging settings: Disable editing of the SMS center number</a></p></td>
<td><p>To meet market or mobile operator requirements, OEMs can configure a setting to prevent users from editing the <strong>SMS center number</strong> in the messaging settings CPL.</p></td>
</tr>
<tr class="even">
<td><p><a href="display-cmas-message-order.md" data-raw-source="[Messaging settings: Display CMAS message order](display-cmas-message-order.md)">Messaging settings: Display CMAS message order</a></p></td>
<td><p>Partners can configure the order in which newly received CMAS alert messages are displayed on the device.</p></td>
</tr>
<tr class="odd">
<td><p><a href="emergency-notifications.md" data-raw-source="[Messaging settings: Emergency notifications](emergency-notifications.md)">Messaging settings: Emergency notifications</a></p></td>
<td><p>Partners can turn on support for various government emergency notification programs.</p></td>
</tr>
<tr class="even">
<td><p><a href="extract-phone-numbers-in-strings.md" data-raw-source="[Messaging settings: Extract phone numbers in strings](extract-phone-numbers-in-strings.md)">Messaging settings: Extract phone numbers in strings</a></p></td>
<td><p>Partners can extend the entity extraction feature that recognizes phone numbers in text. This customization allows strings of numbers that are concatenated to a string to be recognized.</p></td>
</tr>
<tr class="odd">
<td><p><a href="international-assisted-dialing-for-sms.md" data-raw-source="[Messaging settings: International assisted dialing for SMS](international-assisted-dialing-for-sms.md)">Messaging settings: International assisted dialing for SMS</a></p></td>
<td><p>If partners have turned off <a href="assistance-for-dialing-international-phone-numbers.md" data-raw-source="[Assistance for dialing international phone numbers](assistance-for-dialing-international-phone-numbers.md)">Assistance for dialing international phone numbers</a>, partners may still override the MCC and MNC used for plus code replacement when sending SMS.</p></td>
</tr>
<tr class="even">
<td><p><a href="mms-apn-settings.md" data-raw-source="[Messaging settings: MMS APN settings](mms-apn-settings.md)">Messaging settings: MMS APN settings</a></p></td>
<td><p>Partners can choose to display an <strong>add mms apn</strong> or <strong>edit mms apn</strong> button that enables the user to configure the APN used for MMS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="mms-automatic-download.md" data-raw-source="[Messaging settings: MMS automatic download](mms-automatic-download.md)">Messaging settings: MMS automatic download</a></p></td>
<td><p>Partners can choose to display an <strong>Automatically download MMS</strong> toggle to allows users to turn off automatic downloads of MMS messages. If the toggle is displayed, partners can also change the default value to stop automatic MMS downloads.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/library/windows/hardware/mt628525" data-raw-source="[Messaging settings: MMS data options](https://msdn.microsoft.com/library/windows/hardware/mt628525)">Messaging settings: MMS data options</a></p></td>
<td><p>Partners can configure the MMS data options to:</p>
<ul>
<li><p>Show the <strong>Allow MMS if cellular data is off</strong> toggle in the <strong>Messaging</strong> settings screen.</p></li>
<li><p>Allow MMS messaging even if data is turned off.</p></li>
<li><p>Allow MMS messaging even if data is turned off and the user is roaming.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><a href="mms-delivery-confirmation.md" data-raw-source="[Messaging settings: MMS delivery confirmation](mms-delivery-confirmation.md)">Messaging settings: MMS delivery confirmation</a></p></td>
<td><p>Partners can specify whether users receive notification that MMS messages could not be delivered, and determine whether users can control this by using the <strong>MMS delivery confirmation</strong> toggle in the <strong>Messaging</strong> settings screen.</p></td>
</tr>
<tr class="even">
<td><p><a href="mms-for-group-messages.md" data-raw-source="[Messaging settings: MMS for group messages](mms-for-group-messages.md)">Messaging settings: MMS for group messages</a></p></td>
<td><p>For the setting that determines if group messages sent to multiple people must be sent as MMS, partners can customize the setting by hiding or showing the <strong>Group text</strong> toggle in the <strong>Messaging</strong> settings screen, changing the default value, and configuring the option to alert the user of possible additional charges for sending a group text as MMS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="mms-receipt-acknowledgement.md" data-raw-source="[Messaging settings: MMS receipt acknowledgement](mms-receipt-acknowledgement.md)">Messaging settings: MMS receipt acknowledgement</a></p></td>
<td><p>Partners can specify whether the device automatically sends a receipt acknowledgment for MMS messages when messages arrive, and allow users to control the receipt acknowledgments by using the <strong>Send MMS acknowledgement</strong> toggle in the <strong>Messaging</strong> setting screen.</p></td>
</tr>
<tr class="even">
<td><p><a href="sms-delivery-confirmation.md" data-raw-source="[Messaging settings: SMS delivery confirmation](sms-delivery-confirmation.md)">Messaging settings: SMS delivery confirmation</a></p></td>
<td><p>Partners can specify whether users receive notification that SMS messages could not be delivered, and determine whether users can control these notifications by using the <strong>SMS delivery confirmation</strong> toggle in the <strong>Messaging</strong> settings screen.</p></td>
</tr>
<tr class="odd">
<td><p><a href="contact-management-on-the-sim.md" data-raw-source="[People settings: Contact management on the SIM](contact-management-on-the-sim.md)">People settings: Contact management on the SIM</a></p></td>
<td><p>Partners can specify that users should be able to read, edit, delete, import, and export contact information on their SIM (basic SIM, USIM, or RUIM). This customization is only available for devices sold in China.</p></td>
</tr>
<tr class="even">
<td><p><a href="disable-wait-for-phonebook-ready-signal-from-the-modem.md" data-raw-source="[People settings: Disable wait for phonebook ready signal from the modem](disable-wait-for-phonebook-ready-signal-from-the-modem.md)">People settings: Disable wait for phonebook ready signal from the modem</a></p></td>
<td><p>FDN SIM contacts syncs from the SIM during device boot. By default, this component waits until the phonebook ready signal is received from the modem and then it verifies whether FDN contact management is enabled on the SIM. If needed, OEMs can disable the wait for the phonebook ready signal.</p></td>
</tr>
<tr class="odd">
<td><p><a href="hide-contacts-without-phone-numbers.md" data-raw-source="[People settings: Hide contacts without phone numbers](hide-contacts-without-phone-numbers.md)">People settings: Hide contacts without phone numbers</a></p></td>
<td><p>Partners can change the default OS behavior so that both contacts with phone numbers and contacts without phone numbers are shown in the People Hub.</p></td>
</tr>
<tr class="even">
<td><p><a href="sort-order-for-contacts.md" data-raw-source="[People settings: Sort order for contacts](sort-order-for-contacts.md)">People settings: Sort order for contacts</a></p></td>
<td><p>OEMs can use this customization to set the list of contacts displayed in the People Hub to be organized by last name instead of first name or first name instead of last name.</p></td>
</tr>
<tr class="odd">
<td><p><a href="sort-order-for-contacts-override.md" data-raw-source="[People settings: Sort order for contacts override](sort-order-for-contacts-override.md)">People settings: Sort order for contacts override</a></p></td>
<td><p>OEMs can customize the default values for people sort and display settings as documented in the <a href="sort-order-for-contacts.md" data-raw-source="[Sort order for contacts](sort-order-for-contacts.md)">Sort order for contacts</a> customization. However, these settings may be overridden by the defaults for the user’s current locale unless the OEM sets an additional override registry key.</p></td>
</tr>
<tr class="even">
<td><p><a href="assistance-for-dialing-international-phone-numbers.md" data-raw-source="[Phone settings: Assistance for dialing international phone numbers](assistance-for-dialing-international-phone-numbers.md)">Phone settings: Assistance for dialing international phone numbers</a></p></td>
<td><p>Partners can turn off the international assist feature that helps users with the country codes needed for dialing international phone numbers.</p></td>
</tr>
<tr class="odd">
<td><p><a href="call-forwarding.md" data-raw-source="[Phone settings: Call forwarding](call-forwarding.md)">Phone settings: Call forwarding</a></p></td>
<td><p>Partners can hid the user option for call forwarding.</p></td>
</tr>
<tr class="even">
<td><p><a href="conditional-call-forwarding.md" data-raw-source="[Phone settings: Conditional call forwarding](conditional-call-forwarding.md)">Phone settings: Conditional call forwarding</a></p></td>
<td><p>Partners can now show the call forwarding icon for conditional call forwarding as well as unconditional call forwarding.</p></td>
</tr>
<tr class="odd">
<td><p><a href="hide-the-sim-security-settings-option.md" data-raw-source="[Phone settings: Hide the SIM security settings option](hide-the-sim-security-settings-option.md)">Phone settings: Hide the SIM security settings option</a></p></td>
<td><p>OEMs can hide the <strong>SIM security</strong> settings option.</p></td>
</tr>
<tr class="even">
<td><p><a href="long-tones.md" data-raw-source="[Phone settings: Long tones](long-tones.md)">Phone settings: Long tones</a></p></td>
<td><p>Partners can make a user option visible that makes it possible to toggle between short and long DTMF tones.</p></td>
</tr>
<tr class="odd">
<td><p><a href="overriding-the-voicemail-number-on-the-uicc.md" data-raw-source="[Phone settings: Overriding the voicemail number on the UICC](overriding-the-voicemail-number-on-the-uicc.md)">Phone settings: Overriding the voicemail number on the UICC</a></p></td>
<td><p>Mobile operators can override the voicemail number on the UICC with a different voicemail number that is configured in the registry.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/library/windows/hardware/mt762906" data-raw-source="[Phone settings: Trim supplementary service codes](https://msdn.microsoft.com/library/windows/hardware/mt762906)">Phone settings: Trim supplementary service codes</a></p></td>
<td><p>OEMs can trim supplementary service codes to ensure network compatibility. When a code is sent using a USSD string in a ##code# format, <code>EnableSupplementaryServiceEraseToDeactivateOverride</code> trims the USSD string so #code# is sent. This customization applies only to codes that use the ##code# format.</p></td>
</tr>
<tr class="odd">
<td><p><a href="video-over-lte.md" data-raw-source="[Phone settings: Video over LTE](video-over-lte.md)">Phone settings: Video over LTE</a></p></td>
<td><p>Partners can customize specific settings and behavior for Video over LTE to meet mobile operator requirements.</p></td>
</tr>
<tr class="even">
<td><p><a href="voicemail-number-for-cdma-phones.md" data-raw-source="[Phone settings: Voicemail number for CDMA phones](voicemail-number-for-cdma-phones.md)">Phone settings: Voicemail number for CDMA phones</a></p></td>
<td><p>CDMA mobile operator partners who do not have the voicemail numbers on the device SIM can configure the voicemail number for their devices.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/library/windows/hardware/mt628526" data-raw-source="[Phone settings: Wi-Fi calling operator name](https://msdn.microsoft.com/library/windows/hardware/mt628526)">Phone settings: Wi-Fi calling operator name</a></p></td>
<td><p>OEMs can customize the display name for the mobile operator when the device is using Wi-Fi calling.</p></td>
</tr>
<tr class="even">
<td><p><a href="enable-the-incompatible-charger-notification.md" data-raw-source="[USB settings: Enable the incompatible charger notification](enable-the-incompatible-charger-notification.md)">USB settings: Enable the incompatible charger notification</a></p></td>
<td><p>Partners can set the device to display a warning when the user connects the device to an incompatible charging source. This warning is intended to notify users that their device may take longer to charge or may not charge at all with the current charging source.</p></td>
</tr>
<tr class="odd">
<td><p><a href="enable-the-data-connection-prompt.md" data-raw-source="[USB settings: Enable the data connection prompt](enable-the-data-connection-prompt.md)">USB settings: Enable the data connection prompt</a></p></td>
<td><p>Partners can set the device to display a dialog that asks for permission to enable the data connection when the user connects the device to a host computer via a USB cable.</p></td>
</tr>
<tr class="even">
<td><p><a href="hide-the-weak-charger-notification-option-ui.md" data-raw-source="[USB settings: Hide the weak charger notification option UI](hide-the-weak-charger-notification-option-ui.md)">USB settings: Hide the weak charger notification option UI</a></p></td>
<td><p>Partners can configure the device to hide the dialog that is displayed when the user connects the device to an incompatible charging source and hide the USB setting that notifies the user when the device is connected to a slower charger.</p></td>
</tr>
<tr class="odd">
<td><p><a href="cta-app-install-prompts.md" data-raw-source="[Store settings: CTA app install prompts](cta-app-install-prompts.md)">Store settings: CTA app install prompts</a></p></td>
<td><p>To meet China Type Approval (CTA) requirements for devices shipping in China, OEMs must show a notification dialog to alert users when the app being downloaded does certain things.</p></td>
</tr>
<tr class="even">
<td><p><a href="windows-phone-store-for-china.md" data-raw-source="[Store settings: Microsoft Store for China](windows-phone-store-for-china.md)">Store settings: Microsoft Store for China</a></p></td>
<td><p>For a Windows 10 Mobile device shipping in China, OEMs must specify that the device is intended for that market by setting the <strong>PhoneROMLanguage</strong> setting in <strong>DeviceTargetingInfo</strong> to the appropriate locale ID.</p></td>
</tr>
<tr class="odd">
<td><p><a href="display-location-icon.md" data-raw-source="[System tray: Display location icon](display-location-icon.md)">System tray: Display location icon</a></p></td>
<td><p>Partners can hide the location icon in the system tray if they choose.</p></td>
</tr>
</tbody>
</table>

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
