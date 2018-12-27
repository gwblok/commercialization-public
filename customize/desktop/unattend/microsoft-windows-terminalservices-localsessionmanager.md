---
title: Microsoft-Windows-TerminalServices-LocalSessionManager
description: Microsoft-Windows-TerminalServices-LocalSessionManager
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: fd132480-e7ff-4a4f-9754-f9134e9a68e5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-TerminalServices-LocalSessionManager

The Microsoft-Windows-TerminalServices-LocalSessionManager component is responsible for starting the computer and implementing Windows Fast User Switching (FUS). FUS utilizes the data separation technology of user profiles, providing a fast and convenient mechanism for switching between user accounts.

Terminal Services uses terminal emulation to deliver the Windows desktop and Windows-based applications to a wide variety of computers.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [fDenyTSConnections](microsoft-windows-terminalservices-localsessionmanager-fdenytsconnections.md) | Specifies whether remote desktop connections are enabled. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
