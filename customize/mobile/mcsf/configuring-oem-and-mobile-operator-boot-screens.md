---
title: Configuring OEM and mobile operator boot screens
description: Partners must add at least one, and no more than two, boot screens (also called splash screens) that are displayed when the device is turned on. These screens are intended for partners to display branding elements or logos.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3600ee32-c6bc-4f2c-bff5-b0909f772ffb


ms.date: 05/02/2017
ms.topic: article


---

# Configuring OEM and mobile operator boot screens


Partners must add at least one, and no more than two, boot screens (also called *splash screens*) that are displayed when the device is turned on. These screens are intended for partners to display branding elements or logos.

Boot screens are shown only when the device is booting. When the user turns on the device from a sleep state, only the lock screen appears. Boot screens or splash screens that were added are not applied until the next time that the device boots. The runtime configuration engine runs later in the boot sequence (after the splash screens have been shown) so the customization is not visible until the next time the device reboots.

**Limitations and restrictions:**

-   Logos and images must be owned or licensed by the OEM or mobile operator partner.

-   The first two boot screens support 24-bit-per-pixel bitmaps, and they cannot be animated. For more information about the supported bitmap formats, see section 5.2.22.4 of the [ACPI Specification Revision 5.0](http://go.microsoft.com/fwlink/p/?LinkId=267491).

-   The bitmap, along with the (x,y) offset specified in the BGRT table, must fit inside the boundaries specified by the screen resolution.

-   Support for localization is not included. Images and text should be appropriate for the market in which the device will ship.

-   Additional boot screens must not be added to the startup sequence.

-   If the OEM specifies two boot screens (in addition to the Windows 10 Mobile boot screen), the duration for displaying the first boot screen can be configured by the OEM. For more information, see [Configuring the duration of the first boot screen](configuring-the-duration-of-the-first-boot-screen.md). The duration of the other boot screens cannot be altered.

<a href="" id="instructions-"></a>**Instructions:**  
To specify only one boot screen:

-   Update the BGRT table in ACPI to specify the required values to describe the boot screen. In particular, ensure that the **Image Address** field is set to the address of the bitmap to use for the boot screen image, and set the lowest bit of the **Status** field to 1. For more information about the BGRT table, see section 5.2.22 of the [ACPI Specification Revision 5.0](http://go.microsoft.com/fwlink/p/?LinkId=267491). Because the implementation of the BGRT table is specific to the SoC vendor, the SoC vendor may have additional guidance or requirements for these changes.

To specify two boot screens:

1.  Configure the image for the first boot screen to be loaded through UEFI. For more information, consult with the SoC vendor. In this scenario, the image for the first boot screen is not specified in the BGRT table; UEFI firmware alone is responsible for displaying the first boot screen.

2.  For the second boot screen, update the BGRT table in ACPI to specify the required values to describe the second boot screen. In particular, ensure that the **Image Address** field is set to the address of the bitmap to use for the second boot screen image, and set the lowest bit of the **Status** field to 0 (the value 0 indicates that this BGRT table describes the second boot screen image). For more information about the BGRT table, see section 5.2.22 of the [ACPI Specification Revision 5.0](http://go.microsoft.com/fwlink/p/?LinkId=267491). Because the implementation of the BGRT table is specific to the SoC vendor, the SoC vendor may have additional guidance or requirements for these changes.

## Related topics


[Configuring the duration of the first boot screen](configuring-the-duration-of-the-first-boot-screen.md)

[Configuring a boot screen to display in the final boot screen slot](configuring-a-boot-screen-to-display-in-the-final-boot-screen-slot.md)

 

 







