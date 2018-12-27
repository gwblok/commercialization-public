---
title: ColorDepth
description: ColorDepth
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: eb7a0319-84cf-451e-88c6-62227533232c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ColorDepth


`ColorDepth` specifies the bits-per-pixel color depth to apply to the video adapter.

The `ColorDepth` setting is used to configure only Windows PE, and is not applied to the Windows installation. To change the display settings for the Windows installation, see [Display](microsoft-windows-shell-setup-display.md) in the [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) component.

**Note**  
We recommend that you use the default settings. If you select a value for this setting that is not supported by Windows PE, your video adapter, or the display monitor, then Windows PE might show only a blank screen and will not display an error.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>color_depth_bits_per_pixel</em></p></td>
<td><p>Specifies the bits-per-pixel color depth to apply to the video adapter.</p>
<p>For example, to specify a color depth of 32 bits, set <code>ColorDepth</code> to <strong>32</strong>.</p>
<p>The value for <code>ColorDepth</code> must be supported by the video adapter and the display monitor.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [Display](microsoft-windows-setup-display.md) | **ColorDepth**

## Applies To


**Note**  
This setting only affects the Windows Setup process on BIOS-based computers. UEFI-based computers are not affected by these settings.

 

For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output sets the display resolution to 640x480, with 16-bit color depth and a refresh rate of 60 hertz.

```
<Display>
   <HorizontalResolution>640</HorizontalResolution>
   <VerticalResolution>480</VerticalResolution>
   <ColorDepth>16</ColorDepth>
   <RefreshRate>60</RefreshRate>
</Display>
```

## Related topics


[Display](microsoft-windows-setup-display.md)

 

 







