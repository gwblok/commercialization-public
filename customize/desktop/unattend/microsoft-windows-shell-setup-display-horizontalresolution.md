---
title: HorizontalResolution
description: HorizontalResolution
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 25008312-26a2-40cf-8141-4db8178ab5ae
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HorizontalResolution


`HorizontalResolution` specifies the horizontal resolution for the display device.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Resolution</em></p></td>
<td><p>Specifies the horizontal resolution, in pixels. <em>Resolution</em> is an integer.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


auditSystem

auditUser

oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [Display](microsoft-windows-shell-setup-display.md) | **HorizontalResolution**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output sets the display resolution to 1024x768, with 32-bit color depth, a refresh rate of 72 hertz, and 120 dpi.

```
<Display>
   <ColorDepth>32</ColorDepth>
   <DPI>120</DPI>
   <HorizontalResolution>1024</HorizontalResolution>
   <RefreshRate>72</RefreshRate>
   <VerticalResolution>768</VerticalResolution>
</Display>
```

## Related topics


[Display](microsoft-windows-shell-setup-display.md)

 

 







