---
title: HelpCustomized
description: HelpCustomized
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4494d414-b276-4bee-9c98-b358f9e26df2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# HelpCustomized

> [!Important]
> This setting has been deprecated. To customize the Get Help app that ships with Windows 10, define `SupportURL` or `SupportAppURL` as part of your `OEMInformation`.

`HelpCustomized` specifies whether the Original Equipment Manufacturer (OEM) customizes the Get Help app.

## Values

| Value                   | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| **true**                | **Deprecated**. Specifies that Help is customized.                      |
| **false**               | **Deprecated**. Specifies that Help isn't customized. Default value.     |

## Valid Configuration Passes

auditUser

generalize

offlineServicing

oobeSystem

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OEMInformation](microsoft-windows-shell-setup-oeminformation.md) | **HelpCustomized**

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

[HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md)

[Author and Add Custom Help and Support Content](http://go.microsoft.com/fwlink/?LinkId=237145)
