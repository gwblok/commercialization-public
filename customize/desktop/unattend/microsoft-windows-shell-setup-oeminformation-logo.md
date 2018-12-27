---
title: Logo
description: Logo
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a2c55d15-94f5-4b43-a3b9-e3c5453ebf41
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# Logo

> [!Important]
> This setting has been deprecated.

`Logo` specifies the path to the .bmp file of the manufacturer's logo. This logo appears in the **Performance Information and Tools** Control Panel, but is not used in the **Settings** app. In the **Settings** app, no logo displays.

## Values

| Value                   | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| *path_to_logo*          | **This setting has been deprecated**. Specifies the path to the manufacturer's logo. The logo must be located on the destination computer, and it must be a .bmp file. *Path_to_logo* is a string with a maximum length of 256 characters.         |

> [!Note]
> The logo must be in 32-bit color. Logos that are larger than 120x120 pixels are scaled to 120x120.

This string type supports empty elements.

## Valid Configuration Passes

auditUser

generalize

offlineServicing

oobeSystem

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OEMInformation](microsoft-windows-shell-setup-oeminformation.md) | **Logo**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML shows how to set OEM information.

```xml
<OEMInformation>
   <SupportProvider>Contoso Support</SupportProvider>
   <SupportAppURL>contoso-contact-support</SupportAppURL>
   <SupportURL>http://www.fabrikam.com/support</SupportURL>
</OEMInformation>
```

## Related topics

[OEMInformation](microsoft-windows-shell-setup-oeminformation.md)
