---
title: Supporting Usages in Touch Digitizer Drivers (Windows 7)
description: Supporting Usages in Touch Digitizer Drivers (Windows 7)
MS-HAID:
- 'touch\_195a33cf-5f28-4a63-987a-e926c906d418.xml'
- 'p\_weg\_hardware.supporting\_usages\_in\_touch\_digitizer\_drivers'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5e7e96a3-abe7-4df0-88db-a73d13e51906
keywords: ["Windows Touch WDK , touch digitizer driver", "touch digitizer driver WDK Touch", "digitizer driver WDK Touch"]
---

# Supporting Usages in Touch Digitizer Drivers (Windows 7)


In the context of Windows Touch, *touch* refers to support of a single trackable contact point. This topic outlines required and optional HID usages for a touch digitizer driver. If your digitizer device supports more than one contact point, see [Supporting Usages in Multi-touch Digitizer Drivers](supporting-usages-in-multitouch-digitizer-drivers.md).

Usage identifier values are defined in the [HID Usage Tables](http://www.usb.org/developers/hidpage/Hut1_12v2.pdf).

### <a href="" id="required-hid-usages"></a> Required HID Usages

For Windows 7, a touch digitizer must appear through HID as a touch screen (page 0x0D, usage 0x04).

The following usages are required:

-   X (page 0x01, usage 0x30) and Y (page 0x01, usage 0x31)

    Report x and y position location.

-   Tip switch (page 0x0D, usage 0x42)

    Use the tip switch to indicate finger contact and liftoff from the digitizer surface, similar to how a pen reports contact with the digitizer.

-   In-range (page 0x0D, usage 0x32)

    If the device supports z-axis detection, it reports in-range when the transducer is within the region where digitizing is possible. If the device does not support z-axis detection, the driver should set in-range and tip switch when a finger comes in contact with the digitizer.

    Versions of Windows earlier than Windows 7 have different guidelines for how touch digitizer drivers should handle in-range reporting.

### <a href="" id="optional-hid-usages"></a> Optional HID Usages

The following usages are optional, but you should implement them if the digitizer hardware supports them. These usages were added to the USB HID Usage Tables in the Windows Vista timeframe.

-   Confidence (page 0x0D, usage 0x47)

    Confidence is a suggestion from the device about whether the touch contact was an intended or accidental touch. Your device should reject accidental touches as thoroughly as it can and report that information by using the confidence usage. The operating system uses confidence to help improve accidental touch rejection. In addition to the confidence value, Windows 7 applies additional heuristics to the touch input stream to improve accidental touch rejection. If your device does not report confidence, it is completely up to your device to provide accidental touch rejection.

-   Width and height (page 0x0D, usages 0x48 and 0x49)

    The width and height usages represent the width and height of the touch contact. Width and height are also exposed to application developers through the [Windows Touch platform](http://go.microsoft.com/fwlink/p/?linkid=155047).

-   Pressure (page 0x0D, usage 0x30)

    Pressure is a measure of the force that the finger exerts against the digitizer surface.

For a sample touch descriptor, see [Sample Report Descriptor for a Touch Digitizer Device](sample-report-descriptor-for-a-touch-digitizer-device.md).

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_WEG_Hardware\p_weg_hardware%5D:%20Supporting%20Usages%20in%20Touch%20Digitizer%20Drivers%20%28Windows%207%29%20%20RELEASE:%20%285/9/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



