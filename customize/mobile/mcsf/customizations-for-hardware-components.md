---
title: Customizations for hardware components
description: This section contains information about customization settings that OEMs can use for the following hardware components ButtonsCameraDisplayNetworkingSensorsStorageTouch.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 396b31cd-d6ee-4055-b6d2-dad0b7273df9


ms.date: 05/02/2017
ms.topic: article


---

# Customizations for hardware components


This section contains information about customization settings that OEMs can use for the following hardware components:

-   Buttons
-   Camera
-   Display
-   Networking
-   Sensors
-   Storage
-   Touch

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
<td><p><a href="enabling-the-start-button-to-wake-the-phone.md" data-raw-source="[Buttons: Enabling the Start button to wake the phone](enabling-the-start-button-to-wake-the-phone.md)">Buttons: Enabling the Start button to wake the phone</a></p></td>
<td><p>OEMs can configure the Start button to wake up the phone from the sleep state (also sometimes called the idle state). This can be configured on phones with one of the following hardware configurations:</p>
<ul>
<li><p>The phone has a hardware Start button.</p></li>
<li><p>The phone uses capacitive buttons, and the buttons share the same touch controller as the display panel but use separate sense lines, or the buttons have a dedicated touch controller. .</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><a href="improved-user-experience-for-phones-without-a-hw-camera-button.md" data-raw-source="[Camera: Improved user experience for phones without a HW camera button](improved-user-experience-for-phones-without-a-hw-camera-button.md)">Camera: Improved user experience for phones without a HW camera button</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><a href="building-images-for-fwvga-panels-with-static-software-buttons.md" data-raw-source="[Display: Building images for FWVGA panels with static software buttons](building-images-for-fwvga-panels-with-static-software-buttons.md)">Display: Building images for FWVGA panels with static software buttons</a></p></td>
<td><p>OEMs can build images for FWVGA (480 x 854) display panels where the Back, Home, and Search buttons are rendered on the screen by the OS instead of using hardware buttons. In these types of images, the bottom 54 scan lines of the display panel are reserved to render the software buttons.</p></td>
</tr>
<tr class="even">
<td><p><a href="building-images-with-user-managed-software-buttons.md" data-raw-source="[Display: Building images with user-managed software buttons](building-images-with-user-managed-software-buttons.md)">Display: Building images with user-managed software buttons</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><a href="configuring-the-mtu-data-size.md" data-raw-source="[Networking: Configuring the MTU data size](configuring-the-mtu-data-size.md)">Networking: Configuring the MTU data size</a></p></td>
<td><p>For TCP, the default maximum transmission unit (MTU) is set to 1500 bytes, and the maximum segment size (MSS) is 1460 bytes. In general, this value should not be changed, as the user experience will degrade if low values are set. However, if the MSS does not meet the requirements of the mobile operator network, OEMs can customize it by setting the MTU data size.</p></td>
</tr>
<tr class="even">
<td><p><a href="auto-brightness.md" data-raw-source="[Sensors: Auto brightness](auto-brightness.md)">Sensors: Auto brightness</a></p></td>
<td><p>This customization allows partners to customize the brightness by specifying:</p>
<ul>
<li><p>The value of brightness when dimming the screen.</p></li>
<li><p>The ABS millilux range mapping.</p></li>
<li><p>The ABS intensity percent mapping.</p></li>
<li><p>The brightness state transition delay (in seconds).</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><a href="enabling-the-packed-commands-feature-for-emmc.md" data-raw-source="[Storage: Enabling the packed commands feature for eMMC](enabling-the-packed-commands-feature-for-emmc.md)">Storage: Enabling the packed commands feature for eMMC</a></p></td>
<td><p>You can configure the phone to enable the packed commands feature for eMMC parts. This feature packs multiple small read requests in a single transfer request to the eMMC device.</p></td>
</tr>
<tr class="even">
<td><p><a href="enabling-the-uhs-1-feature-for-sd-cards.md" data-raw-source="[Storage: Enabling the UHS-1 feature for SD cards](enabling-the-uhs-1-feature-for-sd-cards.md)">Storage: Enabling the UHS-1 feature for SD cards</a></p></td>
<td><p>You can configure the phone to enable the UHS-1 feature for SD cards. This feature enables a higher bus speed for SD cards that support Ultra High Speed Phase I (UHS-1).</p></td>
</tr>
<tr class="odd">
<td><p><a href="enabling-the-hs200-feature-for-emmc.md" data-raw-source="[Storage: Enabling the HS200 feature for eMMC](enabling-the-hs200-feature-for-emmc.md)">Storage: Enabling the HS200 feature for eMMC</a></p></td>
<td><p>You can configure the device to enable the HS200 feature for eMMC parts. This eMMC feature delivers a theoretical throughput of 200 MB/s across the eMMC bus, using a 200 MHz single data rate clock with an 8-bit bus width. This can result in significant performance improvements, especially on higher-end eMMC parts.</p></td>
</tr>
<tr class="even">
<td><p><a href="defining-capacitive-button-behavior.md" data-raw-source="[Touch: Defining capacitive button behavior](defining-capacitive-button-behavior.md)">Touch: Defining capacitive button behavior</a></p></td>
<td><p>For mobile devices that use capacitive buttons, OEMs must add registry values that specify the number of capacitive buttons, the button locations, the button names, and the values to send to the OS when the button is pressed. This information enables the OS to treat the capacitive buttons below the screen as touchable targets.</p></td>
</tr>
<tr class="odd">
<td><p><a href="describing-the-physical-width-and-height-of-the-display.md" data-raw-source="[Touch: Describing the physical width and height of the display](describing-the-physical-width-and-height-of-the-display.md)">Touch: Describing the physical width and height of the display</a></p></td>
<td><p>As part of implementing support for the touch controller hardware, OEMs must add registry values that specify the physical width and height the portion of the screen that is used to render the mobile device UI. The OS uses this information to properly scale touch gestures and help ensure a fluid user experience.</p></td>
</tr>
<tr class="even">
<td><p><a href="specifying-the-repeat-rate-for-touch-samples-during-touch-and-hold-presses.md" data-raw-source="[Touch: Specifying the repeat rate for touch samples during touch-and-hold presses](specifying-the-repeat-rate-for-touch-samples-during-touch-and-hold-presses.md)">Touch: Specifying the repeat rate for touch samples during touch-and-hold presses</a></p></td>
<td><p>As part of implementing the touch driver, OEMs must determine how to send repeated touch samples to the input reader component in the OS during touch-and-hold presses. OEMs can choose to have the HID touch class driver (TchHID.sys) automatically send duplicate data packets to the input reader component in the OS during touch-and-hold presses, or they can send repeated touch samples from their touch driver. The OEM must add a registry value that tells the OS which implementation they chose, and the repeat rate to use if the OEM chose to have TchHID.sys send duplicate data packets automatically.</p></td>
</tr>
<tr class="odd">
<td><p><a href="removing-cellular-functionality-on-the-mobile-device.md" data-raw-source="[Wi-Fi: Removing cellular functionality on the mobile device](removing-cellular-functionality-on-the-mobile-device.md)">Wi-Fi: Removing cellular functionality on the mobile device</a></p></td>
<td><p>If your mobile device does not support a cellular radio or will not be connected to a cellular network, you can remove all cellular-related functionality from the device&#39;s user interface by adding the WIFI_FEATURE_PACK feature entry in your OEMInput.xml file.</p></td>
</tr>
</tbody>
</table>

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
