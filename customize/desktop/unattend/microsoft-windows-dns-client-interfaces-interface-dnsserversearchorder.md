---
title: DNSServerSearchOrder
description: DNSServerSearchOrder
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2d506257-0ee6-47b6-95f4-dac332cc2f07
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# DNSServerSearchOrder

`DNSServerSearchOrder` specifies a list of IP addresses to use when searching for the DNS server on the network.

When running unattended setup for a DNS client, you can configure a list of suffixes for the DNS client to search and a list of DNS servers to use.

However, the entries are not guaranteed to be applied in any specific order.

To ensure the correct ordering of DNS servers, use [Key](microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder-ipaddress-key.md) in `DNSServerSearchOrder` and [Key](microsoft-windows-dns-client-dnssuffixsearchorder-domainname-key.md) in [DNSSuffixSearchOrder](microsoft-windows-dns-client-dnssuffixsearchorder.md) to specify the order in which each DNS server should be searched. For example,

```XML
   <DNSServerSearchOrder>
      <IpAddress wcm:action="add" wcm:keyValue="2">2001:4898:28:4:213:20ff:fe16:3e96</IpAddress>
      <IpAddress wcm:action="add" wcm:keyValue="3">172.16.1.12</IpAddress>
      <IpAddress wcm:action="add" wcm:keyValue="1">192.168.1.1</IpAddress>
   </DNSServerSearchOrder>
```

You can also use the [Key](microsoft-windows-dns-client-dnssuffixsearchorder-domainname-key.md) setting under [DNSSuffixSearchOrder](microsoft-windows-dns-client-dnssuffixsearchorder.md) element to ensure that suffixes are searched in a specific order. For example,

```XML
   <DNSSuffixSearchOrder>
      <DomainName wcm:action="add" wcm:keyValue="2">fabrikam.com</DomainName>
      <DomainName wcm:action="add" wcm:keyValue="3">server2.fabrikam.com</DomainName>
      <DomainName wcm:action="add" wcm:keyValue="1">server1.fabrikam.com</DomainName>    
      </ DNSSuffixSearchOrder >
```

For both of these examples, the value for [Key](microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder-ipaddress-key.md)in `DNSServerSearchOrder` and [Key](microsoft-windows-dns-client-dnssuffixsearchorder-domainname-key.md) in [DNSSuffixSearchOrder](microsoft-windows-dns-client-dnssuffixsearchorder.md) indicates the order in which the DNS servers are searched. In this example, the server search order list is:

1. 192.168.1.1
1. 2001:4898:28:4:213:20ff:fe16:3e96
1. 172.16.1.12

The suffix search order is:

1. server1.fabrikam.com
1. fabrikam.com
1. server2.fabrikam.com

The value for [Key](microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder-ipaddress-key.md)in `DNSServerSearchOrder` and [Key](microsoft-windows-dns-client-dnssuffixsearchorder-domainname-key.md) in [DNSSuffixSearchOrder](microsoft-windows-dns-client-dnssuffixsearchorder.md) must be unique, and can be set to any alphanumeric character. If the value is numeric (contains only numbers), these will be applied to order the list of [IpAddress](microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder-ipaddress.md) within `DNSServerSearchOrder`.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [IpAddress](microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder-ipaddress.md) | Specifies an IP address. |

## Parent Hierarchy

[Microsoft-Windows-DNS-Client](microsoft-windows-dns-client.md) | [Interfaces](microsoft-windows-dns-client-interfaces.md) | [Interface](microsoft-windows-dns-client-interfaces-interface.md) | **DNSServerSearchOrder**

## Valid Configuration Passes

specialize

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-DNS-Client](microsoft-windows-dns-client.md).

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

[Interface](microsoft-windows-dns-client-interfaces-interface.md)
