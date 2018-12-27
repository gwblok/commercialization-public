---
title: Customize using the mobile MCSF framework
description: The Managed Centralized Settings Framework (MCSF), which was introduced in Windows Phone 8.1, is supported in Windows 10.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 76de8fd4-b393-4cc1-93a8-ae9776c0446e


ms.date: 05/02/2017
ms.topic: article


---

# Customize using the mobile MCSF framework


The Managed Centralized Settings Framework (MCSF), which was introduced in Windows Phone 8.1, is supported in Windows 10.

MCSF consists of both image time and runtime components that enable a simple and consistent way of declaring OS settings, and a centralized framework that the runtime configuration engine, mobile operators, device management servers, and others can query or modify these settings. A runtime configurable MCSF can either be a configuration service provider-based customization or registry-based customization being exposed through the MSCF CSP.

Similar to the Unattend answer file that can be provided to Windows Setup for Windows Desktop image customization, a customization answer file can be passed to customize an image with specific settings and to create variants for the image. The customization answer file allows for a broader integration across the OS by providing OEMs with a single place to define nearly all OS settings. During image build time, the customization answer file is processed and built as customization packages, which are automatically included in the images. OEM partners can leverage this system by defining a registry or configuration service provider-based settings in packages using MCSF. MCSF also produces customization policy files for both OEM partners and Microsoft. These files are extracted from the packages used to build the OS image to determine the valid settings for the OS image.


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
<td><p><a href="managed-centralized-settings-framework-mcsf.md" data-raw-source="[Managed Centralized Settings Framework (MCSF)](managed-centralized-settings-framework-mcsf.md)">Managed Centralized Settings Framework (MCSF)</a></p></td>
<td><p>Provides a standard way to describe settings that are customizable within packages. MCSF also generates a policy based on the settings descriptions. The settings framework can be image time or runtime configurable. A runtime configurable MCSF can either be a configuration service provider-based customization or registry-based customization being exposed through the MSCF CSP.</p></td>
</tr>
<tr class="even">
<td><p><a href="customization-answer-file.md" data-raw-source="[Customization answer file](customization-answer-file.md)">Customization answer file</a></p></td>
<td><p>A <strong>customization answer file</strong> is an XML file that you write based on the MCSF schema. OEMs can use the MCSF customization answer file to specify the settings and variants for a custom mobile OS image. The customization answer file allows for a broader integration across the OS by providing OEMs with a single place to define nearly all mobile OS settings.</p></td>
</tr>
<tr class="odd">
<td><p><a href="set-languages-and-locales.md" data-raw-source="[Set languages and locales](set-languages-and-locales.md)">Set languages and locales</a></p></td>
<td><p>Provides an overview of the different language and locale settings based on the market in which the mobile device will ship.</p></td>
</tr>
<tr class="even">
<td><p><a href="create-a-resource-only-dll-for-localized-strings.md" data-raw-source="[Create a resource-only .dll for localized strings](create-a-resource-only-dll-for-localized-strings.md)">Create a resource-only .dll for localized strings</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><a href="customizations-for-device-management.md" data-raw-source="[Customizations for device management](customizations-for-device-management.md)">Customizations for device management</a></p></td>
<td><p>This section provides more information about device management settings that OEMs can change.</p></td>
</tr>
<tr class="even">
<td><p><a href="customizations-for-hardware-components.md" data-raw-source="[Customizations for hardware components](customizations-for-hardware-components.md)">Customizations for hardware components</a></p></td>
<td><p>This section contains information about customization settings that OEMs can use for the following hardware components:</p>
<ul>
<li>Buttons</li>
<li>Camera</li>
<li>Display</li>
<li>Networking</li>
<li>Sensors</li>
<li>Storage</li>
<li>Touch</li>
</ul></td>
</tr>
<tr class="odd">
<td><p><a href="customizations-for-applications-and-microsoft-components.md" data-raw-source="[Customizations for applications and Microsoft components](customizations-for-applications-and-microsoft-components.md)">Customizations for applications and Microsoft components</a></p></td>
<td><p>This section contains information about customizations related to apps and Microsoft components.</p></td>
</tr>
<tr class="even">
<td><p><a href="customizations-for-boot-initial-setup-and-shutdown.md" data-raw-source="[Customizations for boot, initial setup, and shutdown](customizations-for-boot-initial-setup-and-shutdown.md)">Customizations for boot, initial setup, and shutdown</a></p></td>
<td><p>Use these customizations to configure the device boot, initial setup, or shutdown experience.</p></td>
</tr>
<tr class="odd">
<td><p><a href="customizations-for-browser.md" data-raw-source="[Customizations for browser](customizations-for-browser.md)">Customizations for browser</a></p></td>
<td><p>Describes the customizations for the browser.</p></td>
</tr>
<tr class="even">
<td><p><a href="customizations-for-connectivity.md" data-raw-source="[Customizations for connectivity](customizations-for-connectivity.md)">Customizations for connectivity</a></p></td>
<td><p>Describes the customizations for configuring connectivity settings.</p></td>
</tr>
<tr class="odd">
<td><p><a href="customizations-for-desktop-experiences.md" data-raw-source="[Customizations for desktop experiences](customizations-for-desktop-experiences.md)">Customizations for desktop experiences</a></p></td>
<td><p>Describes the customizations that you can configure for the desktop when the mobile device is connected.</p></td>
</tr>
<tr class="even">
<td><p><a href="customizations-for-email.md" data-raw-source="[Customizations for email](customizations-for-email.md)">Customizations for email</a></p></td>
<td><p>Describes the customizations related to email.</p></td>
</tr>
<tr class="odd">
<td><p><a href="customizations-for-maps.md" data-raw-source="[Customizations for maps](customizations-for-maps.md)">Customizations for maps</a></p></td>
<td><p>Describes the customizations that you can configure for maps on the mobile device.</p></td>
</tr>
<tr class="even">
<td><p><a href="customizations-for-phone-calls.md" data-raw-source="[Customizations for phone calls](customizations-for-phone-calls.md)">Customizations for phone calls</a></p></td>
<td><p>Provides information about customizations you can configure for the phone or dialer app including branding, visual voicemail, caller ID matching, dialer codes, and more.</p></td>
</tr>
<tr class="odd">
<td><p><a href="customizations-for-photos-music-and-videos.md" data-raw-source="[Customizations for photos, music, and videos](customizations-for-photos-music-and-videos.md)">Customizations for photos, music, and videos</a></p></td>
<td><p>Contains the customizations you can configure for photos, music, and videos.</p></td>
</tr>
<tr class="even">
<td><p><a href="customizations-for-settings.md" data-raw-source="[Customizations for Settings](customizations-for-settings.md)">Customizations for Settings</a></p></td>
<td><p>The <strong>Settings</strong> app contains a predefined collection of user-configurable system settings that&#39;s organized into pages by functionality. As specified in policy, the appearance and default values of these settings are generally not customizable. The following table contain the complete list of user-facing settings that OEMs and mobile operators can change.</p></td>
</tr>
<tr class="odd">
<td><p><a href="customizations-for-sms-and-mms.md" data-raw-source="[Customizations for SMS and MMS](customizations-for-sms-and-mms.md)">Customizations for SMS and MMS</a></p></td>
<td><p>Contains settings that you can configure for SMS and MMS.</p></td>
</tr>
<tr class="even">
<td><p><a href="customizations-for-start.md" data-raw-source="[Customizations for Start](customizations-for-start.md)">Customizations for Start</a></p></td>
<td><p>This section contains information about customizations related to Start.</p></td>
</tr>
</tbody>
</table>

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)
