---
title: Microsoft-Windows-TerminalServices-RemoteConnectionManager
description: Microsoft-Windows-TerminalServices-RemoteConnectionManager
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e34a6cdf-9088-4020-8a2b-a96651aa9ac1
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-TerminalServices-RemoteConnectionManager

Microsoft-Windows-TerminalServices-RemoteConnectionManager configures how Terminal Services manages Client Access Licenses (CALs).

> [!Note]
> This component is ignored unless the Windows feature **AppServer** **(Terminal Services Application Server)** is enabled in the Windows image.

 

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [LicensingMode](microsoft-windows-terminalservices-remoteconnectionmanager-licensingmode.md) | Specifies whether Client Access Licenses (CALs) are configured on a per-user or per-device basis. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
