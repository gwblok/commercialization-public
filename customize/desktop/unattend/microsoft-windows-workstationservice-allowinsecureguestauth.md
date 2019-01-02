---
title: AllowInsecureGuestAuth
description: Specifies whether the SMB client will allow insecure guest logons to an SMB server.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# AllowInsecureGuestAuth

`AllowInsecureGuestAuth` specifies whether the SMB client will allow insecure guest logons to an SMB server.

Insecure guest logons are used by file servers to allow unauthenticated access to shared folders. While uncommon in an enterprise environment, insecure guest logons are frequently used by consumer Network Attached Storage (NAS) appliances acting as file servers. Windows file servers require authentication and do not use insecure guest logons by default.

> [!Important]
> Since insecure guest logons are unauthenticated, important security features such as SMB Signing and SMB Encryption are disabled. As a result, clients that allow insecure guest logons are vulnerable to a variety of man-in-the-middle attacks that can result in data loss, data corruption, and exposure to malware. Additionally, any data written to a file server using an insecure guest logon is potentially accessible to anyone on the network. Microsoft recommends disabling insecure guest logons and configuring file servers to require authenticated access.

## Values

| Value                          | Description                                                                                    |
|:-------------------------------|:-----------------------------------------------------------------------------------------------|
| 0                              | SMB client rejects insecure guest logons. <br/>This is the default, and recommended, value.    |
| 1                              | SMB client allows insecure guest logons.                                                       |

## Valid Configuration Passes

generalize

## Parent Hierarchy

[Microsoft-Windows-WorkstationService](microsoft-windows-workstationservice.md) | **AllowInsecureGuestAuth**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-WorkstationService](microsoft-windows-workstationservice.md).

## XML Example

The following XML output shows how to enable the SMB client to allow insecure guest logons to an SMB server.

```XML
<settings pass="generalize">
    <component name="Microsoft-Windows-WorkstationService" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
        <AllowInsecureGuestAuth>1</AllowInsecureGuestAuth>
    </component>
</settings>
```

## Related topics

[Microsoft-Windows-WorkstationService](microsoft-windows-workstationservice.md)
