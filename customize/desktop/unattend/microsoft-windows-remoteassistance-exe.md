---
title: Microsoft-Windows-RemoteAssistance-Exe
description: Microsoft-Windows-RemoteAssistance-Exe
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d0fac731-479c-4ef6-8b4c-e4f72c2087d0
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-RemoteAssistance-Exe

The Microsoft-Windows-RemoteAssistance-Exe component enables a user with a computer problem to receive assistance from another person who is located elsewhere. The helper can be a friend or a support professional. In the corporate environment, the helper is usually an employee receiving help from the corporate IT helpdesk. In the home environment, the user is often receiving help from a friend or a family member who is a power user and is remotely located.

To enable remote assistance, you must configure the Windows Firewall. Use the [FirstLogonCommands](microsoft-windows-shell-setup-firstlogoncommands.md) setting to create a command that configures Windows Firewall. Use `Netsh` to enable Remote Assistance. For example,

`netsh advfirewall firewall set rule group="Remote Assistance" new enable=yes`

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
[CreateEncryptedOnlyTickets](microsoft-windows-remoteassistance-exe-createencryptedonlytickets.md) | Specifies whether only encrypted tickets are created. |
| [fAllowToGetHelp](microsoft-windows-remoteassistance-exe-fallowtogethelp.md) | Specifies that a user can request help from a friend or a support professional. |
| [fAllowFullControl](microsoft-windows-remoteassistance-exe-fallowfullcontrol.md) | Specifies that a friend or a support professional can take control of the computer of the person requesting assistance. |
| [MaxTicketExpiry](microsoft-windows-remoteassistance-exe-maxticketexpiry.md) | Specifies the maximum amount of time that a ticket can live. |
| [MaxTicketExpiryUnits](microsoft-windows-remoteassistance-exe-maxticketexpiryunits.md) | Specifies the units for the maximum amount of time that a ticket can live. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
