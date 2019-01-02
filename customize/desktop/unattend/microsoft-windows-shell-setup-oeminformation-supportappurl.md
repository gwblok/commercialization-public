---
title: SupportAppURL
description: SupportAppURL specifies the OEM-built support app that will be launched instead of the web URL.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: DB690B4B-4FCC-4074-97D7-C339BB8C24D3
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# SupportAppURL

`SupportAppURL` specifies the OEM-built support app that will be launched from the Get Help app.

## Values

Set the value to your app's protocol handler, which is the value that's registered in your app's manifest file.

For example, in the following app manifest file snippet, the **Protocol Name** is **contoso-contact-support** so this will be the value that will be used for `SupportAppURL`:

```xml
      <Extensions>
        <uap:Extension Category="windows.protocol">
          <uap:Protocol Name="contoso-contact-support">
            <uap:DisplayName>contoso-resource:appDisplayName</uap:DisplayName>
          </uap:Protocol>
        </uap:Extension>
      </Extensions>
```

This value is required, unless [`SupportURL`](microsoft-windows-shell-setup-oeminformation-supporturl.md) is present, in which case it is optional. If both are supplied, `SupportAppURL` is used. Add a parameter with a unique value to identify traffic coming from the Get Help app.

## Valid Configuration Passes

auditUser

generalize

offlineServicing

oobeSystem

specialize

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OEMInformation](microsoft-windows-shell-setup-oeminformation.md) | **SupportAppURL**

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
