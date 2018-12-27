---
title: Microsoft-Windows-SMBServer
description: Microsoft-Windows-SMBServer
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bb52c2be-e22a-4ac1-ac4e-db0d25c94b2a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-SMBServer

The Microsoft-Windows-SMBServer (Server Message Block) component provides the integration and the authentication for Windows client computers to access network printers and file systems that run on UNIX servers. Computers running Windows must have a clear text registry patch and an SMBServer mapping to use SMBServer.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [LmAnnounce](microsoft-windows-smbserver-lmannounce.md) | Specifies whether the server sends LanMan or Net BIOS messages to announce its presence. |
| [Size](microsoft-windows-smbserver-size.md) | Specifies the size of the cache. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
