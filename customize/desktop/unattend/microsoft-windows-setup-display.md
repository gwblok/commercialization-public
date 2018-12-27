---
title: Display
description: Display
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bb6fd5f9-5888-47dc-b561-949f1860f01f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Display

`Display` contains display settings for a video adapter.

The `Display` setting is used during the Windows PE phase of the Windows installation process. The display settings are not applied to the Windows installation. To change the display settings for the Windows installation, see [Display](microsoft-windows-shell-setup-display.md) in the [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) component.

We recommend that you use the default settings. If you select a value for this setting that is not supported by Windows PE, your video adapter, or the display monitor, then Windows PE might show only a blank screen without displaying an error.

> [!Note]
> On UEFI-based computers, this setting is ignored unless you have added a graphics driver into the Windows PE image at \\sources\\boot.wim.
> On BIOS-based computers, by default, Windows PE uses a resolution of 1024x768. For displays with a smaller maximum resolution, Windows PE uses the largest resolution available, based on the extended display identification data (EDID) of the connected display.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [ColorDepth](microsoft-windows-setup-display-colordepth.md) | Specifies the color depth to apply to the display device. |
| [HorizontalResolution](microsoft-windows-setup-display-horizontalresolution.md) | Specifies the horizontal resolution to apply to the display device. |
| [RefreshRate](microsoft-windows-setup-display-refreshrate.md) | Specifies the refresh rate to apply to the display device. |
| [VerticalResolution](microsoft-windows-setup-display-verticalresolution.md) | Specifies the vertical resolution to apply to the display device. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[microsoft-windows-setup-](microsoft-windows-setup.md) | **Display**

## Applies To

This setting only affects the Windows Setup process on BIOS-based computers. UEFI-based computers are not affected by these settings.

For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output sets the display resolution to 1920x1080, with 16-bit color depth and a refresh rate of 60 hertz.

```XML
<Display>
   <HorizontalResolution>1920</HorizontalResolution>
   <VerticalResolution>1080</VerticalResolution>
   <ColorDepth>16</ColorDepth>
   <RefreshRate>60</RefreshRate>
</Display>
```

## Related topics

[Microsoft-Windows-Setup](microsoft-windows-setup.md)
