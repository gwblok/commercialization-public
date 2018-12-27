---
title: Customizations for boot, initial setup, and shutdown
description: Use these customizations to configure the device boot, initial setup, or shutdown experience.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d6dc354b-1579-4f73-acaa-c28d700c75ec


ms.date: 05/02/2017
ms.topic: article


---

# Customizations for boot, initial setup, and shutdown


Use these customizations to configure the device boot, initial setup, or shutdown experience.

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
<td><p><a href="configure-the-timezone-confirmation-page-during-setup.md" data-raw-source="[Configure the timezone confirmation page during setup](configure-the-timezone-confirmation-page-during-setup.md)">Configure the timezone confirmation page during setup</a></p></td>
<td><p>Use to allow users to change the timezone and region during device setup.</p></td>
</tr>
<tr class="even">
<td><p><a href="configuring-a-boot-screen-to-display-in-the-final-boot-screen-slot.md" data-raw-source="[Configuring a boot screen to display in the final boot screen slot](configuring-a-boot-screen-to-display-in-the-final-boot-screen-slot.md)">Configuring a boot screen to display in the final boot screen slot</a></p></td>
<td><p>By default, the Windows 10 Mobile logo is displayed as the final boot screen. However, partners can display a different screen for the final boot screen slot. The image must be in .JPG, .JPEG, or .PNG format.</p></td>
</tr>
<tr class="odd">
<td><p><a href="configuring-boot-battery-charging-behavior.md" data-raw-source="[Configuring boot battery charging behavior](configuring-boot-battery-charging-behavior.md)">Configuring boot battery charging behavior</a></p></td>
<td><p>The boot (UEFI) environment contains a battery charging application (owned by Microsoft) that is responsible for charging the battery in pre-boot and low power states. OEMs can configure some of the behavior of this application by using the registry values described in this topic.</p></td>
</tr>
<tr class="even">
<td><p><a href="configuring-oem-and-mobile-operator-boot-screens.md" data-raw-source="[Configuring OEM and mobile operator boot screens](configuring-oem-and-mobile-operator-boot-screens.md)">Configuring OEM and mobile operator boot screens</a></p></td>
<td><p>Partners must add at least one, and no more than two, boot screens (also called <em>splash screens</em>) that are displayed when the device is turned on. These screens are intended for partners to display branding elements or logos.</p></td>
</tr>
<tr class="odd">
<td><p><a href="configuring-the-duration-of-the-first-boot-screen.md" data-raw-source="[Configuring the duration of the first boot screen](configuring-the-duration-of-the-first-boot-screen.md)">Configuring the duration of the first boot screen</a></p></td>
<td><p>If partners specify two boot screens (in addition to the Windows 10 Mobile boot screen), they can modify the duration of the first boot screen. We recommend that partners choose a duration for the first boot screen so that the first and second boot screens appear for the same amount of time.</p></td>
</tr>
<tr class="even">
<td><p><a href="custom-shutdown-screen.md" data-raw-source="[Custom shutdown screen](custom-shutdown-screen.md)">Custom shutdown screen</a></p></td>
<td><p>Partners can add a static logo or background during shutdown.</p></td>
</tr>
<tr class="odd">
<td><p><a href="language-selection-during-initial-setup.md" data-raw-source="[Language selection during initial setup](language-selection-during-initial-setup.md)">Language selection during initial setup</a></p></td>
<td><p>If multiple display languages are included on the device, partners have the option of hiding the <strong>Language selection</strong> screen during setup.</p></td>
</tr>
<tr class="even">
<td><p><a href="partner-account-configuration-during-setup.md" data-raw-source="[Partner account configuration during setup](partner-account-configuration-during-setup.md)">Partner account configuration during setup</a></p></td>
<td><p>In Windows 10 Mobile, an OEM or mobile operator may specify one preloaded app to be launched at the end of setup to walk users through an OEM or mobile operator account setup.</p>
<p>Optionally, an OEM or mobile operator may also preload an additional 4 apps that can be subroutined and called from a main app. In this case, the partner specifies one of the apps as the hub app (main app), which will be automatically launched at the end of setup. This app can then invoke other spoke apps (subroutined apps) to complete other tasks.</p></td>
</tr>
<tr class="odd">
<td><p><a href="screen-background-color-during-initial-setup.md" data-raw-source="[Screen background color during initial setup](screen-background-color-during-initial-setup.md)">Screen background color during initial setup</a></p></td>
<td><p>For Windows 10 Mobile, the default background during OOBE or initial device setup is always dark. To align with this change, OEMs can no longer change the default screen background color during OOBE or initial device setup.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/specifying-the-iccid-strings-and-region" data-raw-source="[Set the default country/region when SIM PIN is on](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/specifying-the-iccid-strings-and-region)">Set the default country/region when SIM PIN is on</a></p></td>
<td><p>OEMs can customize the default home country/region that shows up during OOBE in cases where the SIM PIN is turned on. This value is associated with the default ICCID values. When SIM PIN is turned off, the OS uses the MCC-derived country/region instead.</p></td>
</tr>
</tbody>
</table>

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
