---

Description: 'DPI-related APIs and registry settings'
ms.assetid: 23b0e272-a09e-4081-a129-d330b6878d8e
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'DPI-related APIs and registry settings'

ms.date: 05/02/2017
ms.topic: article


---

# DPI-related APIs and registry settings


If you need to perform deployment customizations, the following sections explain the registry keys and system parameters that your post-installation scripts might need to access.

**In this topic:**

-   [Primary display native resolution](#native)

-   [Primary display DPI scale factor](#scale)

-   [Scaling mode](#scalingmode)

-   [Scaling override in Windows 8.1 scaling mode](#override)

-   [System-wide scale factor in Windows 8 scaling mode](#system)


## <span id="native"></span><span id="NATIVE"></span>Primary display native resolution


*Table 1 Windows 8.1 Scaling Levels*, while by no means exhaustive, provides information on the Windows 8.1 scaling level for a number of common displays. **Panel DPI** indicates the physical pixel density of the panel, and **Scaling level** indicates the scale factor that will be used for this display.

**Table 1 Windows 8.1 Scaling Levels**

| Display size | Display resolution | Horizontal (pixels) |	Vertical (pixels) |	Panel DPI |	Scaling level |
| --- | --- | --- | --- | --- | --- |
| 10.6" | FHD | 1920 | 1080 | 208 | 150% |
| 10.6" | HD | 1366 | 768 | 148 | 100% |
| 11.6" | WUXGA | 1920 | 1200 | 195 | 150% |
| 11.6" | HD | 1366 | 768 | 135 | 100% |
| 13.3" | WUXGA | 1920 | 1200 | 170 | 150% |
| 13.3" | QHD | 2560 | 1440 | 221 | 200% |
| 13.3" | HD | 1366 | 768 | 118 | 100% |
| 15.4" | FHD | 1920 | 1080 | 143 | 125% |
| 15.6" | QHD+ | 3200 | 1800 | 235 | 200% |
| 17" | FHD | 1920 | 1080 | 130 | 125% |
| 23" | QFHD (4K) | 3840 | 2160 | 192 | 200% |
| 24" | QHD | 2560 | 1440 | 122 | 125% |

 

To programmatically find this information for any device, you can write a utility program that reports back data. The native primary resolution is retrieved by calling the API [GetDeviceCaps() function](http://go.microsoft.com/fwlink/p/?linkid=331144), using the hdc for the desktop and the HORZRES and VERZRES indices:

```
// Get desktop dc
desktopDc = GetDC(NULL);
// Get native resolution
horizontalResolution = GetDeviceCaps(desktopDc,HORZRES);
verticalResolution = GetDeviceCaps(desktopDc,VERZRES);
```

For more information about GetDC, see [GetDC() function](http://go.microsoft.com/fwlink/p/?linkid=331145).

## <span id="scale"></span><span id="SCALE"></span>Primary display DPI scale factor


Similarly, you can get the pixel density by using the LOGPIXELSX and LOGPIXELSY indices:

```
// Get desktop dc
desktopDc = GetDC(NULL);
// Get native resolution
horizontalDPI = GetDeviceCaps(desktopDc,LOGPIXELSX);
verticalDPI = GetDeviceCaps(desktopDc,LOGPIXELSY);
```

These results are returned in a coordinate system in which 96 corresponds to 100%, as shown in *Table 2 DPI Scale Factors*.

**Table 2 DPI Scale Factors**

| DPI | Scale factor |
| --- | --- |
| 96 | 100 |
| 120 | 125 |
| 144 | 150 |
|192 | 200 |

 

**Note**  
This API will return different results depending on the DPI awareness mode of your application. Configuring the awareness mode requires adding XML to the application manifest, as detailed below:

| DPI Awareness Mode | Manifest Setting | Returned Value |
| ------------------ | ---------------- | -------------- |
| None               | None             |  96 for all displays, regardless of the scale factor |
| System DPI Aware      | \<dpiAware>True\</dpiAware> | The DPI of the primary display at the time the Windows session was started (when the user first logged in to Windows) |
| Per-Monitor DPI Aware | \<dpiAware>True/PM\</dpiAware> | The DPI of the primary display at the time the Windows session was started (when the user first logged in to Windows). To obtain the DPI of the display that the application is located on, use [GetWindowDpi()](https://msdn.microsoft.com/en-us/library/windows/desktop/mt748624.aspx) or [GetDpiForMonitor()](https://msdn.microsoft.com/en-us/library/windows/desktop/dn280510.aspx) |


For more information about this manifest setting, see [SetProcessDPIAware function](http://go.microsoft.com/fwlink/p/?linkid=331146).

## <span id="scalingmode"></span><span id="SCALINGMODE"></span>Scaling mode


The **Control Panel\\ Appearance and Personalization\\Display** user interface (UI) includes a checkbox: **Let me choose one scaling level for all my displays**, which controls whether the system applies a single scale factor to all displays (as in Windows 8 and earlier versions of Windows), or different scale factors that take into account the pixel density of each display (the Windows 8.1 default). This checkbox configures the **HKCU\\Control Panel\\Desktop\\Win8DpiScaling** registry key in Windows 8.1.

**Table 3 HKCU\\Control Panel\\Desktop\\Win8DpiScaling Values**

| Key value | Meaning |
| --- | --- |
| 0 | Different scale factors for each display: Windows 8.1 default.Content that is moved from one display to another will be the right size, but can be bitmap-scaled. |
| 1 | Same scale factor is applied to all displays: Windows 8 and earlier Windows versions behavior. Content that is moved from one display to another might be the wrong size. |

 

## <span id="override"></span><span id="OVERRIDE"></span>Scaling override in Windows 8.1 scaling mode


When the **Let me choose one scaling level for all my displays** checkbox is cleared and the system is running in the Windows 8.1 scaling mode, the user is provided with a slider that lets them override the current scale factors, from Smaller, to Medium, to Larger. This setting is configured in the **HKCU\\Control Panel\\Desktop\\DesktopDPIOverride** registry key.

**Table 4 HKCU\\Control Panel\\Desktop\\DesktopDPIOverride Values**

| Key value | Meaning |
| ---- | ---- |
| <0 | Reduce each display scale factor from the default by this value (for example, if the default was 150% scaling, -1 corresponds to 125%, -2 to 100%). |
| 0 | Use the default value for each display. |
| 0> | Increase each display factor by this value (using the previous example, +1 corresponds to 200% scaling). |

 

All display scale factors in this mode are constrained to be one of these four values: 100%, 125%, 150%, 200%. In addition, after scaling is applied, applications expect to have at least 720 effective lines of resolution (that is, the physical vertical resolution of the display divided by the scale factor); this can further limit the range of allowed display scale factors. *Table 5 Display Values* shows which values are allowed for different sized displays:

**Table 5 Display Values**

| Vertical lines | Supported scale factors |
| --- | --- |
| <900 | 100% |
| >= 900 and <1080 | 100%, 125% |
| >=1080 and <1440 | 100%, 125%, 150% |
| >=1440 | 100%, 125%, 150%, 200% |

 

## <span id="system"></span><span id="SYSTEM"></span>System-wide scale factor in Windows 8 scaling mode


When the **Let me choose one scaling level for all my displays** checkbox is checked, the user can specify a scale factor that applies to all displays, regardless of each display’s pixel density. By using the custom setting, the user can select values other than 100%, 125%, 150%, 200%, although they are limited to the range (100%-500%). This setting is configured in the **HKCU\\Control Panel\\Desktop\\LogPixels** registry key.

**Table 6 HKCU\\Control Panel\\Desktop\\LogPixels Values**

| Key value | Meaning |
| --- | --- |
| 96 | 100% scaling on every display |
| 120 | 125% scaling on every display |
| 144 | 150% scaling on every display |
| 192 | 200% scaling on every display |
| \<other> | \<other> 96/100 scaling on every display |

 
## <span id="related_topics"></span>Related topics

[Documentation for developing High DPI applications](https://msdn.microsoft.com/library/windows/desktop/dd464646.aspx)

[High DPI Support for IT Professionals](high-dpi-support-for-it-professionals.md)

 

 






