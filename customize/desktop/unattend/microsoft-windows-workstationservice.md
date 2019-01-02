---
title: Microsoft-Windows-WorkstationService
description: Microsoft-Windows-WorkstationService
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a53ce7f4-04bf-47be-98de-3361423459cc
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# Microsoft-Windows-WorkstationService

The `Microsoft-Windows-WorkstationService` component creates and maintains client network connections to remote servers, by using the Server Message Block (SMB) protocol.

Client systems use the SMB protocol to request file, print, and communications services from server systems over a network.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AllowInsecureGuestAuth](microsoft-windows-workstationservice-allowinsecureguestauth.md) | Specifies whether an SMB client allows insecure guest logons to an SMB server. |
| [OtherDomains](microsoft-windows-workstationservice-otherdomains.md) | Specifies Microsoft LAN Manager domains to be listed for browsing. |
| [SyncDomainWithMembership](microsoft-windows-workstationservice-syncdomainwithmembership.md) | Specifies whether the primary Domain Name Service (DNS) suffix changes when domain membership changes. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
