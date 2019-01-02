---
title: OverlayFlags
description: Specifies whether writes to unused space on the volume are allowed to pass through without being redirected to the overlay file


ms.date: 10/17/2017
ms.topic: article


---
# OverlayFlags

`OverlayFlags` specifies whether to allow writes to unused space on the volume to pass through, and not be redirected to the overlay file. Enabling this setting helps conserve space on the overlay file.

> [!Note]
> This setting is not intended to be enabled for a systems with a RAM [OverlayType](microsoft-windows-embedded-unifiedwritefilter-overlaytype.md).

## Values

| Value      | Description                                                       |
|:-----------|:------------------------------------------------------------------|
| 0          | Writes are redirected to the overlay file. <br/>This is the default value when the [OverlayType](microsoft-windows-embedded-unifiedwritefilter-overlaytype.md) is not `Disk overlay`     |
| 1          | Writes to unused space on the volume are allowed to pass through without being redirected to the overlay file. <br/>This is the default when the [OverlayType](microsoft-windows-embedded-unifiedwritefilter-overlaytype.md) is `Disk overlay`    |

## Parent Hierarchy

[Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md) | **OverlayFlags**

## Valid Configuration Passes

specialize

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md).

## XML Example

```XML
<settings pass="specialize">
   <component name="Microsoft-Windows-Embedded-UnifiedWriteFilter" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <OverlayFlags>1</OverlayFlags>
   </component>
</settings>
```
