---
title: Microsoft-Windows-DNS-Client
description: Microsoft-Windows-DNS-Client
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2b227e7a-3738-42b3-af78-b3a98f7d8412
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-DNS-Client

The Microsoft-Windows-DNS-Client component contains settings for configuring the Domain Name System (DNS), a system for naming computers and network services that organizes them into a hierarchy of domains. DNS naming is used on TCP/IP networks, such as the Internet, to locate computers and services by using user-friendly names.

The DNS Client service is used to resolve DNS domain names, by querying locally cached information obtained from a previous query or by querying a remote DNS server.

Some settings are global, and others are interface-specific. Global settings apply to all network adapters on the computer. Interface-specific settings apply only to a single interface and may overlap with global settings.

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DNSDomain](microsoft-windows-dns-client-dnsdomain.md) | Specifies the primary DNS suffix of the network connection across all adapters. If <code>DNSDomain</code> is specified in two places as a global parameter (x) and as an interface-specific parameter (y), the two values are concatenated appropriately for each interface (as x, y) and used. |
| [DNSSuffixSearchOrder](microsoft-windows-dns-client-dnssuffixsearchorder.md) | Specifies the suffix search order for DNS servers. This is a global setting. |
| [Interfaces](microsoft-windows-dns-client-interfaces.md) | Specifies an interface collection. |
| [UseDomainNameDevolution](microsoft-windows-dns-client-usedomainnamedevolution.md) | Specifies whether to use domain-name devolution when the DNS-caching resolver resolves an unqualified query. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
