---
title: Microsoft-Windows-UnattendedJoin
description: Microsoft-Windows-UnattendedJoin
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 89ea05a9-6b5d-460b-a6de-1f542b17ae6a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-UnattendedJoin

The Microsoft-Windows-UnattendedJoin component enables a computer to join a domain during the specialize or OfflineServicing configuration pass. By joining a computer to a domain, you can apply policies to the computer and access additional resources on the domain.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Identification](microsoft-windows-unattendedjoin-identification.md) | Specifies credentials to join a domain, the name of the domain to join, the workgroup to assign to the computer, and other options during the specialize configuration pass. |
| [OfflineIdentification](microsoft-windows-unattendedjoin-offlineidentification.md) | Specifies the account information used to join a domain during Windows Setup. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
