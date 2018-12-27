---
title: CEIPEnabled
description: CEIPEnabled
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4f57233c-4856-473f-ab6e-7a6506b6a59b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# CEIPEnabled

`CEIPEnabled` indicates whether the Windows Customer Experience Improvement Program (CEIP) is enabled.

If the Microsoft-Windows-SQMAPI component is enabled, it collects and sends data to Microsoft about Windows usage. Participation in this program is voluntary, and the results are recorded to implement improvements for future releases.

This setting has no effect on Server Core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012.

## Values

| Value                | Description                                                                              |
|:---------------------|:-----------------------------------------------------------------------------------------|
| 0                    | Specifies that Windows CEIP is chosen during OOBE. If the user decides to skip OOBE during installation, CEIP will be opted out. The user receives no further notifications.                                                                                |
| 1                    | Specifies that Windows CEIP collects and sends anonymous data to Microsoft to help improve Windows.<br/>This is the default value. |
 
## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-SQMAPI](microsoft-windows-sqmapi.md) | **CEIPEnabled**

## Applies To

For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-SQMAPI](microsoft-windows-sqmapi.md).

## XML Example

The following XML output disables Windows CEIP.

```XML
<CEIPEnabled>0</CEIPEnabled>
```

## Related topics

[Microsoft-Windows-SQMAPI](microsoft-windows-sqmapi.md)
