---
title: PageFile
description: PageFile
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a9d773c1-dd21-4b38-83a0-ecd65c9b1529
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# PageFile

`PageFile` specifies the location and the size of the Windows PE operating system page file to create. This setting applies only to the Windows PE page file, and not to the page file of the Windows installation.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Path](microsoft-windows-setup-pagefile-path.md) | Specifies the path of the page file to create. |
| [Size](microsoft-windows-setup-pagefile-size.md) | Specifies the size of the page file to create. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | **PageFile**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output shows how to create a page file.

```XML
<PageFile>
   <Path>%WINDIR%\MyPagefile.sys</Path>
   <Size>512</Size>
</PageFile>
```

## Related topics

[Microsoft-Windows-Setup](microsoft-windows-setup.md)
