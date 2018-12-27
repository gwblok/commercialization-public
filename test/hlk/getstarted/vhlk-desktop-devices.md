---
title: VHLK Connecting Desktop Clients
description: Information and Guidance for Connecting Desktop Clients to the Windows Virtual Hardware Lab Kit (VHLK)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 10/02/2018
ms.topic: article
ms.custom: RS5
---

# Connecting Desktop Client Devices to the VHLK

## Before Starting
* The desktop HLK Client is paired with the controller. For every new HLK Controller, HLK Client on your desktop client must be re-installed.
* If the desktop client has previously had the HLK Client installed:
    * Uninstall Windows Hardware Lab Kit Client through "Add or Remove Programs"
    * Re-install from \\<ControllerName>\HLKInstall\Client\Setup.cmd.
* Make sure network visibility and file & printer sharing is enabled, as described in the setup guide.
* Make sure that your desktop device and the HLK Controller VM can ping each other by both IPV4 address and name.
* Make sure that the HLK Controller computer name is resolved to an IPV4 address by your desktop device, and vice versa.

## Start Testing
At this point, the VHLK and the traditional HLK can be treated as the same product and used in the same way. Follow the [HLK Getting Started Guide](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/getstarted/windows-hlk-getting-started) from Step 2 onwards to connect your client devices and start testing.  
