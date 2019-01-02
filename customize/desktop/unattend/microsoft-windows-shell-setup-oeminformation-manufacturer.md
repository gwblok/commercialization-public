---
title: Manufacturer
description: Manufacturer
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c3d9d4bc-2fa4-4260-bb7b-b2e4bee243fb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# Manufacturer

> [!Important]
> This setting has been deprecated. The Manufacturer name displayed in the Get Help app is now based on your System Manufacturer value defined in System Information (msinfo32.exe), unless you provide a [`SupportProvider`](microsoft-windows-shell-setup-oeminformation-supportprovider.md) parameter as part of your `OEMInformation`. When `SupportProvider` is provided, it will override the System Manufacturer name. This enables you to differentiate the name of your support app or website from the name of your brand if desired (i.e. "Contact Contoso Support" vs "Contact Contoso"). For this release, if `SupportProvider` is not present but the deprecated value `Manufacturer` is, it will still be used to support upgrade scenarios.

`Manufacturer` specifies the name of the manufacturer.

## Values

| Value                   | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| *manufacturer*          | **This setting has been deprecated**. Specifies the name of the manufacturer. *Manufacturer* is a string with a maximum length of 256 characters.                                                                                         |

This string type supports empty elements.

## Valid Configuration Passes

auditUser

generalize

offlineServicing

oobeSystem

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OEMInformation](microsoft-windows-shell-setup-oeminformation.md) | **Manufacturer**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

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
