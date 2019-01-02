---
title: Display
description: Display
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7060a68c-cd05-4fee-a0cc-92538e1a1d6d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Display

`Display` specifies the display settings for the display device.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [ColorDepth](microsoft-windows-shell-setup-display-colordepth.md) | Specifies a valid color depth for the display device in bits per pixel. |
| [HorizontalResolution](microsoft-windows-shell-setup-display-horizontalresolution.md) | Specifies a valid horizontal resolution for the display device. |
| [RefreshRate](microsoft-windows-shell-setup-display-refreshrate.md) | Specifies a valid refresh rate for the display device. |
| [VerticalResolution](microsoft-windows-shell-setup-display-verticalresolution.md) | Specifies a valid vertical resolution for the display device. |

> [!Note]
> If the specified settings cannot be set on the display device, Windows attempts to match the requested mode as closely as possible.

## Valid Configuration Passes

auditSystem

auditUser

oobeSystem

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **Display**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML output sets the display resolution to 1024x768, with 32-bit color depth, and a refresh rate of 72 hertz.

```XML
<Display>
   <ColorDepth>32</ColorDepth>
   <HorizontalResolution>1024</HorizontalResolution>
   <RefreshRate>72</RefreshRate>
   <VerticalResolution>768</VerticalResolution>
</Display>
```

The following XML output sets the display resolution to 1024x768, with 32-bit color depth, a refresh rate of 72 hertz, and displays text and graphics items at a medium size.

```XML
<Display>
   <ColorDepth>32</ColorDepth>
   <DPI>120</DPI>
   <HorizontalResolution>1024</HorizontalResolution>
   <RefreshRate>72</RefreshRate>
   <VerticalResolution>768</VerticalResolution>
</Display>
```

## Related topics

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)
