---
title: Microsoft-Windows-SQMAPI
description: Microsoft-Windows-SQMAPI
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 381c2174-c3e5-42ce-91f2-252165f55817
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-SQMAPI

The Microsoft-Windows-SQMAPI component implements the Windows Customer Experience Improvement Program (CEIP). If the component is enabled, it collects and sends data to Microsoft about the use of Windows. Participation in this program is voluntary, and the results are recorded to implement improvements in future releases.

This setting has no effect on Server Core installations.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [CEIPEnabled](microsoft-windows-sqmapi-ceipenabled.md)   | Specifies whether Windows CEIP is enabled.                                               |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## XML Example

The following XML output shows how to enable Windows CEIP.

```XML
<CEIPEnabled>true</CEIPEnabled>
```

## Related topics

[Components](components-b-unattend.md)
