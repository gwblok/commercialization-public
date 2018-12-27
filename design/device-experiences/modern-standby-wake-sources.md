---
title: Modern Standby wake sources
description: This topic describes the scenarios in which the devices in this PC must be able to wake the processor.
MS-HAID:
- 'cstandby.connected\_standby\_wake\_sources'
- 'p\_weg\_hardware.modern\_standby\_wake\_sources'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
author: beneluxboy
ms.assetid: 4DB2F090-A0AD-4167-8805-85930FEF926F

ms.date: 10/26/2018
ms.topic: article


---

# Modern Standby wake sources


A PC that supports the Modern Standby power model must be capable of waking from standby in response to certain events, even if the platform has entered a very low-power idle state.

This topic describes the types of wake sources that must be able to wake the processor. It also explains which wake events should turn the screen on and which wake events should allow the screen to stay turned off. System integrators should use this information to ensure that their hardware platforms, firmware, and software can configure wake sources to achieve the required behavior.

## Overview of Modern Standby user experience for wake


The Modern Standby user experience is designed to model that of a cellular phone. When users finish using their phones, they press the system power button and the cell phone enters sleep mode. The phone remains asleep until the user presses the power button again, or a phone call, email, or instant message is received.

Similarly, when a PC is in Modern Standby, it looks and feels off—the screen is blanked, the system has no visible LED indicators, and there is no acoustic noise. However, a PC in Modern Standby remains on and connected to the Internet, just as the cell phone remains connected to the cellular network. (The Modern Standby PC uses any available network connection—Wi-Fi, mobile broadband (MBB)/cellular, or wired Ethernet.) And the Modern Standby PC, connected or not, also has very long battery life in its screen-off state, just like a cell phone.

Enabling the Modern Standby user experience requires all of the devices and software in the Modern Standby PC to actively and correctly participate in system power management. Achieving long standby battery life is primarily a function of allowing all devices, plus the core silicon or System on a Chip (SoC), to enter a very low-power idle state. During Modern Standby, the networking subsystem stays connected so that the system can wake and instantly respond to incoming emails or VoIP calls. Enabling the real-time nature of Modern Standby is primarily a function of platform devices waking the SoC for the correct events at the correct times.

All wake sources in the Modern Standby PC are expected to be capable of waking the SoC from its deepest idle power state. Some wake sources should be capable of generating a wake signal for an event that would cause the system display to turn on. The difference between waking the SoC and turning on the display is central to delivering the Modern Standby user experience. The following rules govern platform wake behavior:

-   Wake source operation and scenarios are the same for all Modern Standby PCs, regardless of whether they are based on the x86 or ARM processor architecture.
-   Wake source operation may differ depending on whether the system is plugged in (AC power) or on battery power (DC power). Differences are noted in the tables below.
-   Some wake sources are hardware-dependent, e.g. wake on fingerprint or wake on optical disc drive ejection (some Modern Standby systems may not have a fingerprint reader or optical disc drive). Modern Standby systems are recommended to support all wake scenarios for which they have the necessary hardware.

The remainder of this topic describes the different types of wake sources, along with additional information, such as whether the wake source can turn on a device's display, whether it is enabled by default, and any differences in operation depending on whether a device is on AC or DC power. Please note that the information in this topic applies to systems with Connected Standby enabled. Connected Standby is enabled by selecting "Never" in the following Power & sleep setting:

When my PC is asleep and on battery power, disconnect from the network:
1. Never 
2. Always 
3. Managed by Windows  

Most systems enable Connected Standby by default.  


## Types of wake sources


### Real-time clock (RTC) or always-on timer


The core silicon or SoC chip in a Modern Standby platform has one or more timers that are always powered on that so that Windows can schedule future work and place the SoC into a deep idle state. During standby, the always-on timer reliably wakes the SoC as programmed by the OS.


### Buttons and lid


The system power button is a very common user-initiated wake source in a Modern Standby platform. All Modern Standby PCs must be designed so that the power button is always enabled to send a wake interrupt to the SoC. To deliver an instant-on experience, the power button must cause the SoC to wake from the deepest idle state without delay. Another common user-initiated wake source on clamshell form factor devices is opening the lid, which wakes the SoC. The Windows button is also able to wake the SoC. 


### Communications devices


The Wi-Fi, Ethernet, and mobile broadband (MBB) devices are responsible for delivering the real-time and constant connectivity features of Modern Standby. They facilitate wake sources such as Universal Windows Platform (UWP) Applications notifications and syncing and Bluetooth notifications and syncing.


### Input devices


We recommend using HIDI2C for input peripherals whenever possible for better power efficiency, but this is not a requirement. If necessary, USB can be used to connect to an input device such as a touchpad, touch digitizer, or pen digitizer. A precision touchpad must be capable of waking the system from deep idle, regardless of whether this device is connected to USB or I2C. As an option, a non-precision touchpad can wake the system from deep idle. Touch digitizers and pen digitizers must not wake the system from deep idle.

In addition to buttons on the chassis, a Modern Standby PC might have other input devices physically integrated into the system or attached to the system directly or indirectly through a dock. When the user generates input through an input device, it must always wake the SoC from the deepest idle state and cause the display to turn on.


### Voice input


On devices that are Wake on Voice-capable, voice input of "Hey Cortana" from the user can wake the SoC from the deepest idle state and cause the display to turn on.


### Insertion or removal of a connector or device


When the user inserts or removes certain types of connectors or devices, these events can wake the SoC from the deepest idle state and cause the display to turn on.


### Windows Update


Windows Update can always wake the SoC from the deepest idle state to scan for updates. It can also wake the SoC to download and install updates and restart a device, depending on a device's power source.


### Universal Windows Platform (UWP) Applications 


UWP applications can wake the SoC from the deepest idle state to sync and display notifications, depending on a device's power source, notification priority levels, and app-specific user configurations.


### Remote Access


Remote Desktop and File Sharing can wake the SoC from the deepest idle state on the client system when the system has an Ethernet connection.


### Audio


Audio from internal speakers or Bluetooth speakers can wake the SoC, so that audio continues playing even when a device's screen is off.  


### Environmental context changes


The Modern Standby PC must also respond in real-time to changes in environmental conditions. The common cases are thermal events and power source change events.


## Wakes SoC and **can** turn on display


### Buttons and lid


<table>
<thead>
<tr class="header">
<th>Device</th>
<th>Turns on the display - AC power</th>
<th>Turns on the display - DC power</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Power button</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>The Windows power manager will turn on the display when the power-button interrupt occurs.</p></td>
</tr>
<tr class="even">
<td><p>Windows button</p></td>
<td><p>Yes (if wake-enabled)</p></td>
<td><p>Yes (if wake-enabled)</p></td>
<td><p>The Windows power manager will be notified that the Windows button was pressed and will turn on the screen. The Windows button is considered to be user input.</p></td>
</tr>
<tr class="odd">
<td><p>Lid switch (mechanical or sensor-based)</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>There might be multiple types of lid switches, all of which are exposed to Windows in the same way. The lid switch can be a mechanical-contact switch or sensor-based switch. The platform can expose a lid switch for turning off the display when a tablet is attached to a keyboard dock that is closed. If the tablet has a cover, the sensor for detecting cover closing is also treated as a lid switch.</p>
<p>Opening the lid, opening the cover, or adjusting the display to make it visible must cause the display to automatically turn on. The Windows power manager automatically turns on the display in response to the lid switch interrupt.</p></td>
</tr>
</tbody>
</table>



### Input devices


<table>
<thead>
<tr class="header">
<th>Device</th>
<th>Turns on the display - AC power</th>
<th>Turns on the display - DC power</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Keyboard (integrated HIDI2C)</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>The Windows power manager will turn on the display when keyboard input is detected.</p>
<p>All keys on the keyboard must generate a GPIO wake interrupt and cause the display to turn on (with the exception of volume buttons, which should not turn on the screen).</p>
<p>If the keyboard exposes consumer control keys—such as volume up/down and brightness—these keys must also generate a GPIO wake interrupt.</p>
<div class="alert">
<strong>Note</strong>  If the keyboard is not visible to a user who is interacting with the display (as in a convertible tablet), we recommend that the keyboard not wake the SoC in that mode.
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td><p>Keyboard (external USB)</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Depending on the USB host controller, more than one key press might be required to generate a resume event that causes the screen to turn on.</p></td>
</tr>
<tr class="odd">
<td><p>Keyboard (external Bluetooth)</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Touchpad (integrated HIDI2C)</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Moving a finger on the touchpad or exerting button activation force on the digitizer surface should cause a wake event.</p>
<div class="alert">
<strong>Note</strong><br/><ul>
<li>We recommend a precision touchpad wakes the SoC, though this is optional for either a precision touchpad or a non-precision touchpad.</li>
<li>If the touchpad is not visible to a user who is interacting with the display (as in a convertible tablet), we recommend that the touchpad not wake the SoC in that mode.</li>
</ul>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td><p>Touchpad (external USB)</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Moving a finger on the touchpad or exerting button activation force on the digitizer surface should cause a wake event.</p>
<div class="alert">
<strong>Note</strong><br/><ul>
<li>We recommend a precision touchpad wakes the SoC, though this is optional for either a precision touchpad or a non-precision touchpad.</li>
<li>If the touchpad is not visible to a user who is interacting with the display (as in a convertible tablet), we recommend that the touchpad not wake the SoC in that mode.</li>
</ul>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td><p>Mouse (external USB)</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>At a minimum, pressing any button on the mouse should generate a resume event and cause the screen to turn on. Depending on the USB host controller, more than one button press might be required to cause the screen to turn on. It is an optional capability for the mouse to support generating a resume event and waking the system for any movement of the mouse other than pressing a button.</p></td>
</tr>
<tr class="odd">
<td><p>Mouse (external Bluetooth)</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>At a minimum, pressing any button on the mouse will generate a resume event and cause the screen to turn on. It is an optional capability for the mouse to support generating a resume event and waking the system for any movement of the mouse other than pressing a button. For a USB-connected Bluetooth mouse, the Bluetooth radio event is not followed by a GPIO interrupt.</p></td>
</tr>
<tr class="odd">
<td><p>Fingerprint reader</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


### Voice input


<table>
<thead>
<tr class="header">
<th>Event</th>
<th>Turns on the display - AC power</th>
<th>Turns on the display - DC power</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Voice input (&quot;Hey Cortana&quot;)</p></td>
<td><p>Yes, if the device is Wake on Voice-capable.</p></td>
<td><p>Yes, if the device is Wake on Voice-capable and has a hardware keyword spotter. If the device has a software keyword spotter only, Wake on Voice will be turned off by default on DC power.</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


### Insertion or removal of a connector or device


<table>
<thead>
<tr class="header">
<th>Device</th>
<th>Turns on the display - AC power</th>
<th>Turns on the display - DC power</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Attaching/removing a dock</p></td>
<td><p>Varies.</p>
<p>Depends on the devices in the dock and their current state.</p></td>
<td><p>Varies.</p>
<p>Depends on the devices in the dock and their current state.</p></td>
<td><p>Attaching a dock should be treated the same as individually attaching each of the devices included in the dock.</p>
<p>For example, attaching a dock alone should not cause the SoC to wake. Instead, detection of new devices (I²C device, battery, AC power source, and so on) contained in the dock should cause the SoC to wake.</p></td>
</tr>
<tr class="even">
<td><p>Optical disc drive, including Zero-Power Optical Disc Drive (ZPODD): disc insertion/ejection</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>For ZPODD, the event is a GPE event handled by a storage stack component.</p></td>
</tr>
</tbody>
</table>


### Windows Update


<table>
<thead>
<tr class="header">
<th>Event</th>
<th>Turns on the display - AC power</th>
<th>Turns on the display - DC power</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Restart</p></td>
<td><p>Yes</p></td>
<td><p>No. Restart for Windows Update is disabled on DC power.</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


### Universal Windows Platform (UWP) Applications 


<table>
<thead>
<tr class="header">
<th>Event</th>
<th>Turns on the display - AC power</th>
<th>Turns on the display - DC power</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Skype: incoming calls</p></td>
<td><p>Yes, unless disabled by the user.</p></td>
<td><p>Yes, unless disabled by the user.</p></td>
<td><p>See Note.</p></td>
</tr>
<tr class="even">
<td><p>Skype: incoming IMs</p></td>
<td><p>Yes, unless disabled by the user.</p></td>
<td><p>Yes, unless disabled by the user.</p></td>
<td><p>See Note.</p></td>
</tr>
<tr class="odd">
<td><p>3rd party VoIP calls</p></td>
<td><p>Depends on the type of notification.</p></td>
<td><p>Depends on whether the app is exempt, the notification priority level, and the type of notification.</p></td>
<td><p>See Note.</p></td>
</tr>
<tr class="even">
<td><p>3rd party IMs</p></td>
<td><p>Depends on the type of notification.</p></td>
<td><p>Depends on whether the app is exempt, the notification priority level, and the type of notification.</p></td>
<td><p>See Note.</p></td>
</tr>
<tr class="odd">
<td><p>Bluetooth device notification</p></td>
<td><p>Depends on the type of notification.</p></td>
<td><p>No</p></td>
<td><p>See Note.</p></td>
</tr>
<tr class="even">
<td><p>Bluetooth authentication: proximity</p></td>
<td><p>Depends on the type of notification.</p></td>
<td><p>No</p></td>
<td><p>See Note.</p></td>
</tr>
<tr class="odd">
<td><p>Location services (geofencing APIs trigger push notification)</p></td>
<td><p>Depends on the type of notification and whether the app uses geofencing.</p></td>
<td><p>Depends on whether the app is exempt, whether the app uses geofencing, the notification priority level, and the type of notification.</p></td>
<td><p>See Note.</p></td>
</tr>
<tr class="even">
<td><p>Location services (geovisits APIs trigger push notification)</p></td>
<td><p>Depends on the type of notification and whether the app uses geovisits.</p></td>
<td><p>No</p></td>
<td><p>See Note.</p></td>
</tr>
<tr class="odd">
<td><p>Other UWP apps: push notifications</p></td>
<td><p>Depends on the type of notification.</p></td>
<td><p>Depends on whether the app is exempt, the notification priority level, and the type of notification.</p></td>
<td><p>See Note.</p></td>
</tr>
</tbody>
</table>


**Note** When a device is on AC power, notifications of all priorities from UWP apps will be delivered. When a device is on DC power, high priority, medium priority, and low priority notifications from exempt UWP apps will be delivered. The priority level of different types of notifications is app-specific. For example, Inbox Mail app incoming mail notifications are low priority. For notifications that are delivered during Modern Standby, typically only toast notifications will turn on the display. Raw notifications could also turn on the display, depending on the type of payload they are delivering. For more information about UWP app notifications, please refer to [WNS Notification Priorities](https://docs.microsoft.com/en-us/windows/uwp/design/shell/tiles-and-notifications/wns-notification-priorities).

To set an app as exempt, go to Settings > Battery > See which apps are affecting your battery life, select an app and uncheck the "Let Windows decide when this app can run in the background." To allow notifications from apps, ensure Settings > Notifications and Actions > Notifications > "Get notifications from apps and other senders" is enabled. 

Skype is exempt by default. To change settings for Skype incoming calls, go to Settings > System > Notifications and Actions > Notifications > Show reminders and incoming VoIP calls on the lock screen. To change other Skype notification settings, go to Settings > System > Notifications and Actions > Get notifications from these senders > Skype. 

To configure location services settings and see which apps are using geofencing, the user can navigate to Settings > Privacy  > Location. To find out if an app uses geovisits APIs, please contact the app developer.


### Remote Access

<table>
<thead>
<tr class="header">
<th>Event</th>
<th>Turns on the display - AC power</th>
<th>Turns on the display - DC power</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Remote Desktop</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>The system must have an Ethernet connection. This is not enabled on Wi-Fi.</p></td>
</tr>
</tbody>
</table>


### Environmental context changes


<table>
<thead>
<tr class="header">
<th>Event</th>
<th>Turns on the display - AC power</th>
<th>Turns on the display - DC power</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Power source change (AC to battery, or battery to AC)</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>The Windows power manager will turn on the display when the battery subsystem has indicated a power source change. The GPIO interrupt for power source changes must cause the ACPI _PSR method under the power supply device to be executed.</p>
<p>The power subsystem must wake the SoC any time the power source changes, including when the system is attached or removed from a dock that has a battery or AC power source.</p> After the power source change, the display will remain on for five seconds, unless there is input to the system during this five-second window.</td>
</tr>
</tbody>
</table>

**Note**  When the battery charge level crosses either the low or critical level, Windows briefly turns on the display to present a visual notification of the charge status to the user. This behavior is implemented in Windows and does not require additional firmware support.


## Wakes SoC but **cannot** turn on display


### Real-time clock (RTC) or always-on timer


<table>
<thead>
<tr class="header">
<th>Device</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Always-on timer</p></td>
<td><p>Each SoC has a different mechanism for programming the always-on timer.</p></td>
</tr>
</tbody>
</table>


### Insertion or removal of a connector or device


<table>
<thead>
<tr class="header">
<th>Device</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>SD card insertion/removal (SDIO controller-attached)</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>SD card insertion/removal (USB-attached)</p></td>
<td><p>The SD controller selected must be capable of detecting card insertion and removal while in the USB suspend state drawing less than 1 milliwatt average.</p></td>
</tr>
<tr class="odd">
<td><p>Headphone or microphone insertion/removal</p></td>
<td><p>Attaching a headphone or microphone to the system provides an interrupt to enable the audio stack to correctly route audio.</p></td>
</tr>
<tr class="even">
<td><p>eSATA insertion/removal</p></td>
<td></td>
</tr>
</tbody>
</table>


### Communications devices


<table>
<thead>
<tr class="header">
<th>Device</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Wi-Fi radio</p></td>
<td><p>The Wi-Fi wake source is not required for Disconnected Standby systems. </p></td>
</tr>
<tr class="even">
<td><p>Mobile broadband (MBB) radio</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Bluetooth radio</p></td>
<td><p>Windows and its drivers are responsible for detecting the type of associated Bluetooth device. If a keyboard, mouse, or other user-input device is responsible for causing the Bluetooth radio to wake the SoC, the display will turn on. Other Bluetooth devices such as portable audio headphones will not cause the display to turn on.</p></td>
</tr>
<tr class="even">
<td><p>Wired LAN (USB-attached, Modern Standby-capable)</p></td>
<td><p>Wired LAN devices in Modern Standby platforms or their supported docks must support pattern-match offloads in order to be Modern Standby-capable.</p></td>
</tr>
</tbody>
</table>


**Note**  Windows can turn on the display when an incoming critical alert or activity is detected over the network. Examples include high priority notifications from lock-screen applications and VoIP calls.


### Windows Update

<table>
<thead>
<tr class="header">
<th>Event</th>
<th>Enabled by default - AC power</th>
<th>Enabled by default - DC power</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Scan</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Download</p></td>
<td><p>Yes</p></td>
<td><p>Yes, but only limited to interactive download. All non-interactive downloads are paused. No new downloads will be initiated.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Install</p></td>
<td><p>Yes</p></td>
<td><p>No. In-progress installs get paused. Does not kick off new install.</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

### Remote Access 

<table>
<thead>
<tr class="header">
<th>Event</th>
<th>Enabled by default - AC power</th>
<th>Enabled by default - DC power</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="even">
<td><p>File Sharing</p></td>
<td><p>Yes</p></td>
<td><p>No</p></td>
<td><p>The system must have an Ethernet connection. This is not enabled on Wi-Fi.</p></td>
</tr>
</tbody>
</table>

### Universal Windows Platform (UWP) Applications

<table>
<thead>
<tr class="header">
<th>Event</th>
<th>Enabled by default - AC power</th>
<th>Enabled by default - DC power</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Background upload/download of content</p></td>
<td><p>Yes</p></td>
<td><p>No</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Inbox Mail app: mail sync</p></td>
<td><p>Yes</p></td>
<td><p>No, unless the app is exempt.</p></td>
<td><p>See Note.</p></td>
</tr>
<tr class="odd">
<td><p>Inbox People app: contact sync</p></td>
<td><p>Yes</p></td>
<td><p>No, unless the app is exempt.</p></td>
<td><p>See Note.</p></td>
</tr>
<tr class="even">
<td><p>Inbox Calendar app: calendar sync</p></td>
<td><p>Yes</p></td>
<td><p>No, unless the app is exempt.</p></td>
<td><p>See Note.</p></td>
</tr>
<tr class="odd">
<td><p>Sync with Bluetooth devices</p></td>
<td><p>Yes</p></td>
<td><p>No</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>App operations that require network (via SocketActivityTrigger)</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>OneNote and VoiceRecorder: background audio recording</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

**Note** When a device is on AC power, notifications of all priorities from UWP apps will be delivered. When a device is on DC power, high priority, medium priority, and low priority notifications from exempt UWP apps will be delivered. The priority level of different types of notifications is app-specific. For example, Inbox Mail app incoming mail notifications are low priority. For notifications that are delivered during Modern Standby, typically only toast notifications will turn on the display. Raw notifications could also turn on the display, depending on the type of payload they are delivering. For more information about UWP app notifications, please refer to [WNS Notification Priorities](https://docs.microsoft.com/en-us/windows/uwp/design/shell/tiles-and-notifications/wns-notification-priorities).

To set an app as exempt, go to Settings > Battery > See which apps are affecting your battery life, select an app and uncheck the "Let Windows decide when this app can run in the background." To allow notifications from apps, ensure Settings > Notifications and Actions > Notifications > "Get notifications from apps and other senders" is enabled. 


### Audio

<table>
<thead>
<tr class="header">
<th>Event</th>
<th>Enabled by default - AC power</th>
<th>Enabled by default - DC power</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Audio local and streaming playback (internal speakers) during screen off</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Audio local and streaming playback (Bluetooth speakers) during screen off</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Low Power Audio is not currently supported for Bluetooth speakers, so audio will play during Modern Standby but not be low power.</p></td>
</tr>
</tbody>
</table>


### Environmental context changes


<table>
<thead>
<tr class="header">
<th>Event</th>
<th>Remarks</th>
</tr>
</thead>
<tbody valign="top">
<tr class="odd">
<td><p>Thermal event</p></td>
<td><p>All temperature sensors must wake the SoC from the deepest power state to indicate temperature change.</p>
<p>ACPI firmware should monitor thermal zone temperature changes continuously during standby and when the SoC is in the deepest idle state. The ACPI firmware should report to the Windows thermal manager when the temperature rises above the trip points.</p></td>
</tr>
<tr class="even">
<td><p>Battery charge completion</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Battery threshold change</p></td>
<td><p>The battery subsystem must wake the SoC from its deepest idle state anytime the remaining capacity goes below the value specified by Windows in the _BTP control method.</p>
<p>The battery subsystem must wake the SoC from its deepest idle state anytime the remaining capacity goes below the value specified by DesignCapacityOfLow in the _BIX control method. Windows will hibernate (x86) or shut down (ARM) the system when the remaining capacity falls below DesignCapacityOfLow.</p></td>
</tr>
</tbody>
</table>

