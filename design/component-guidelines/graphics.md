---
title: Graphics
description: Graphics
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 342F222D-15CC-4503-9C82-032F9C2EEC17

ms.date: 05/02/2017
ms.topic: article


---

# Graphics


## Windows 10 Guidelines

This topic covers guidelines for Graphics in Windows 10.

### Windows 10 support for Ultra High Definition (UHD)

Windows supports 4K UHD and 8K UHD, but UHD is more than just higher resolution. These factors affect how people perceive images, in order of importance:

-   Dynamic range, which is the difference between the darkest black and the whitest white, and the steps in between. UHD dynamic range allows users to see details in both the bright and dark portions of an image.
-   Color gamut, which is the range of colors that can be faithfully recreated. UHD has a greatly expanded color gamut and bit depth.
-   Frame rate, which is the number of frames per second. A higher frame rate (50/60fps) makes motion smoother, especially for sporting events.
-   Resolution, which is the number of pixels. 4K resolution (2160p) has 4 times as many pixels as 1080p.

Where it makes sense, display panel manufacturers are recommended to invest in brighter panels, wider color gamuts, higher bit depths, and higher resolutions.

### UHD investments in Windows 10

-   HEVC decoder with hardware offload
-   HEVC encoder with hardware offload
-   Hardware DRM for PlayReady
-   Support for wider color gamut
-   Support for greater precision (color accuracy)

### High Efficiency Video Coding (HEVC)

HEVC (also known as H.265) is a joint MPEG/ITU standard. It is non-proprietary and the successor to Advanced Video Coding (AVC, also known as H.264). Because it has significantly better compression, HEVC can consume up to 30-50% less bandwidth and storage than AVC. It allows the transmission of high quality video across connections that have low bandwidth.

### Content protection

Full 1080p, including 4K UHD, demands higher bar than existing software-based Digital Rights Management (DRM). Windows 10 supports hardware-based content protection. Hardware-based DRM is required to access premium content.

The infrastructure used for hardware-based content protection for Windows 10 is PlayReady 3.0, which provides these benefits:

-   Hardware root of trust
-   Device binding and all keys in hardware
-   Compressed and uncompressed content not exposed to attack
-   Output protections managed by hardware

### Aspect ratios

-   Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) supports any aspect ratio, as in Windows 8.1
-   Windows 10 Mobile will support any aspect ratio by Oct 2015
-   Certain aspect ratios were targeted during design:

    -   Phones: 16:9; Small tablets 16:10
    -   2-in-1’s 3:2; Laptops/Desktops/TVs 16:9
    -   Windows itself will reflow to support an arbitrary aspect ratio
    -   "Square" aspect ratios (&lt;4:3) may have limited scale factor support due to the 4:3 aspect ratio of the minimum effective resolution (800x600 for desktop, 480x800 for mobile)

## Minimum requirements for Graphics

For details on minimum requirements for Graphics, see [Minimum Hardware Requirements](https://docs.microsoft.com/en-us/windows-hardware/design/minimum/minimum-hardware-requirements-overview)