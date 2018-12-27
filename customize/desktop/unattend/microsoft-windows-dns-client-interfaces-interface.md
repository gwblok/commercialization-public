---
title: Interface
description: Interface
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a869644a-8437-4230-8ca7-0c63bb7fef09
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Interface

`Interface` contains interface-specific settings for a Domain Name System (DNS) interface.

DNS settings can be divided into two primary groups—global settings and interface settings. Global settings apply to the protocols as a whole and are applied across all network interfaces. Interface settings are specific to a particular network interface.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DisableDynamicUpdate](microsoft-windows-dns-client-interfaces-interface-disabledynamicupdate.md) | Specifies whether to register the host (A) and pointer (PTR) resource records dynamically. |
| [DNSDomain](microsoft-windows-dns-client-interfaces-interface-dnsdomain.md) | Specifies the DNS suffix of the network connection across all adapters. If <code>DNSDomain</code> is specified in two places—as a global parameter (x) and as an interface-specific parameter (y)—the two values are concatenated appropriately for each interface (as x, y) and used. |
| [DNSServerSearchOrder](microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder.md) | Specifies a list of addresses to use when searching for the DNS server on the network. |
| [EnableAdapterDomainNameRegistration](microsoft-windows-dns-client-interfaces-interface-enableadapterdomainnameregistration.md) | Specifies whether to register the host (A) and pointer (PTR) resource records for this adapter. If it is not specified, only the [DNSDomain](microsoft-windows-dns-client-dnsdomain.md) value specified in the global parameters is used. |
| [Identifier](microsoft-windows-dns-client-interfaces-interface-identifier.md) | Specifies the interface identifier. |

## Parent Hierarchy

[Microsoft-Windows-DNS-Client](microsoft-windows-dns-client.md) | [Interfaces](microsoft-windows-dns-client-interfaces.md) | **Interface**

## Valid Configuration Passes

specialize

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-DNS-Client](microsoft-windows-dns-client.md).

## XML Example

The following XML output shows a DNS domain configuration for Fabrikam.

```XML
   <DNSDomain>fabrikam.com</DNSDomain>
   <DNSSuffixSearchOrder>
      <DomainName wcm:action="add" wcm:keyValue="1">server1.fabrikam.com</DomainName>
      <DomainName wcm:action="add" wcm:keyValue="2">fabrikam.com</DomainName>
   </DNSSuffixSearchOrder>
   <UseDomainNameDevolution>true</UseDomainNameDevolution>
   <Interfaces>
      <Interface wcm:action="add">
         <Identifier>Local Area Connection</Identifier>
         <DNSDomain>fabrikam.com</DNSDomain>
         <DNSServerSearchOrder>
            <IpAddress wcm:action="add" wcm:keyValue="1">192.168.1.1</IpAddress>
            <IpAddress wcm:action="add" wcm:keyValue="2">192.168.1.2</IpAddress>
         </DNSServerSearchOrder>
         <EnableAdapterDomainNameRegistration>true</EnableAdapterDomainNameRegistration>
         <DisableDynamicUpdate>false</DisableDynamicUpdate>
      </Interface>
      <Interface wcm:action="add">
         <Identifier>Local Area Connection 2</Identifier>
         <DNSDomain>fabrikam.com</DNSDomain>
         <DNSServerSearchOrder>
            <IpAddress wcm:action="add" wcm:keyValue="1">192.168.1.1</IpAddress>
            <IpAddress wcm:action="add" wcm:keyValue="2">2001:4898:28:4:213:20ff:fe16:3e96</IpAddress>
         </DNSServerSearchOrder>
         <EnableAdapterDomainNameRegistration>true</EnableAdapterDomainNameRegistration>
        <DisableDynamicUpdate>false</DisableDynamicUpdate>
      </Interface>
   </Interfaces>
```

## Related topics

[Interfaces](microsoft-windows-dns-client-interfaces.md)
