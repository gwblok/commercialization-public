---
title: SupportPhone
description: SupportPhone
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 38aa8ab4-d36d-4c33-8f1c-f4e35e7852ff
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# SupportPhone

> [!Important]
> This setting has been deprecated.

`SupportPhone` specifies the telephone number(s) to call for support for the OEM.

## Values

| Value                   | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| *phone_number*          | **This setting has been deprecated**. Specifies the support telephone number(s) for the OEM. *Phone_number* is a string with a maximum length of 256 characters.                                                                          |

This string type supports empty elements.

## Valid Configuration Passes

auditUser

generalize

offlineServicing

oobeSystem

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OEMInformation](microsoft-windows-shell-setup-oeminformation.md) | **SupportPhone**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

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
