---
title: DynamicUpdate
description: DynamicUpdate
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 25dd9e6b-db95-46a6-bac2-62b2efdcfcf4
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# DynamicUpdate

`DynamicUpdate` specifies whether to enable Dynamic Updates during Windows Setup. Dynamic Updates search for new Windows Setup files, including drivers and other files, to be used to install the Windows operating system.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Enable](microsoft-windows-setup-dynamicupdate-enable.md) | Specifies whether to enable dynamic updates for installation. |
| [WillShowUI](microsoft-windows-setup-dynamicupdate-willshowui.md) | Specifies in what circumstances to show the user interface (UI) for dynamic updates. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | **DynamicUpdate**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output shows the value for the `DynamicUpdate` setting.

```XML
<DynamicUpdate>
   <Enable>true</Enable>
   <WillShowUI>Never</WillShowUI>
</DynamicUpdate>
```

## Related topics

[Microsoft-Windows-Setup](microsoft-windows-setup.md)

[Dynamic Update and Resulting Internet Communication in Windows 7 and Windows Server 2008 R2](http://go.microsoft.com/fwlink/?LinkId=189355)
