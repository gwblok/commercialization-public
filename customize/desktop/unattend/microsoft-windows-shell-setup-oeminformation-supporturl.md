---
title: SupportURL
description: SupportURL
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 311d7bbd-0973-40b3-95be-07eca2edb0c1
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# SupportURL

`SupportURL` specifies the complete URL of the support page for the OEM that will be launched from the Get Help app.

## Values

| Value                   | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| *url*                   | Specifies the support page URL for the OEM. URL must be a complete URL, including the `http://` prefix. *Url* is a string with a maximum length of 2083 characters. Required, unless [`SupportAppURL`](microsoft-windows-shell-setup-oeminformation-supportappurl.md) is present, in which case it is optional. If both are supplied, `SupportAppURL` is used.                                         |

This string type supports empty elements.

## Valid Configuration Passes

auditUser

generalize

offlineServicing

oobeSystem

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OEMInformation](microsoft-windows-shell-setup-oeminformation.md) | **SupportURL**

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
