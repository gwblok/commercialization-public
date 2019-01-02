---
title: OEMInformation
description: OEMInformation
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8fd731ac-32b3-42b5-a3a0-36e6d567617d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# OEMInformation

`OEMInformation` specifies OEM support information that will display in the Get Help app in Windows 10. This information includes the OEM’s support name, and a link to either the URL of their support website, or the URL or their support app. To learn more about the Get Help app, see [Customize the Get Help app](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/customize-get-help-app).

In Windows 10, the OS disables the help components that shipped in Windows 8 and Windows 8.1 including the Help and Support Windows desktop application (HelpPane.exe). HelpPane.exe will continue to exist in the box, but calls to its interfaces will result in one of two outcomes:

* If the user is offline, the OS launches the Getting Started app.
* If the user is online, the OS opens a browser instance and redirects the browser to an online topic.

This change affects context-sensitive (or F1) help and accessing help from the menus for apps shipped with Windows including the shell.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [SupportProvider](microsoft-windows-shell-setup-oeminformation-supportprovider.md) | Name of OEM support app or website. If not provided, the default Manufacturer name (from msinfo32.exe) will be used.                                  |
| [SupportAppURL](microsoft-windows-shell-setup-oeminformation-supportappurl.md)     | URI for the OEM support app. Required, unless `SupportURL` is present, in which case it is optional. If both are supplied, `SupportAppURL` is used. Add a parameter with a unique value to identify traffic coming from the Get Help app.                                                                    |
| [SupportURL](microsoft-windows-shell-setup-oeminformation-supporturl.md)           | Specifies the URL of the support website for an OEM. Required, unless `SupportAppURL` is present, in which case it is optional. If both are supplied, `SupportAppURL` is used.                        |
| [Manufacturer](microsoft-windows-shell-setup-oeminformation-manufacturer.md)       | **This setting has been deprecated**. The Manufacturer name displayed in the Get Help app is now based on your System Manufacturer value defined in System Information (msinfo32.exe), unless you provide a `SupportProvider` parameter as part of your `OEMInformation`. When `SupportProvider` is provided, it will override the System Manufacturer name. This enables you to differentiate the name of your support app or website from the name of your brand if desired (i.e. "Contact Contoso Support" vs "Contact Contoso"). For this release, if `SupportProvider` is not present but the deprecated value `Manufacturer` is, it will still be used to support upgrade scenarios.                                                                           |
| [Model](microsoft-windows-shell-setup-oeminformation-model.md)                     | **This setting has been deprecated**. The Model name displayed in the Get Help app is now based on your System Product Name value, as defined in System Information (msinfo32.exe).                    |
| [HelpCustomized](microsoft-windows-shell-setup-oeminformation-helpcustomized.md)   | **This setting has been deprecated**. To customize the Get Help app, define `SupportURL` or `SupportAppURL` as part of your `OEMInformation`.   |
| [Logo](microsoft-windows-shell-setup-oeminformation-logo.md)                       | **This setting has been deprecated**. No logo is used in the Get Help app.                                                                        |
| [SupportHours](microsoft-windows-shell-setup-oeminformation-supporthours.md)       | **This setting has been deprecated**. Support hours are not shown in the Get Help app.                                                           |
| [SupportPhone](microsoft-windows-shell-setup-oeminformation-supportphone.md)       | **This setting has been deprecated**. Support phone number is not shown in the Get Help app.                                                       |

## Valid Configuration Passes

auditUser

generalize

offlineServicing

oobeSystem

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **OEMInformation**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following example shows how to set OEM information.

```xml
<OEMInformation>
   <SupportProvider>Contoso Support</SupportProvider>
   <SupportAppURL>contoso-contact-support</SupportAppURL>
   <SupportURL>http://www.fabrikam.com/support</SupportURL>
</OEMInformation>
```

## Related topics

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)

[Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md)
