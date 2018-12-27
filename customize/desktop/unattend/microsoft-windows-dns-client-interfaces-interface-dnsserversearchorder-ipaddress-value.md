---
title: Value
description: Value
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 53fb448a-cd8a-4215-9f19-378da2d6ba88
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Value


`Value` specifies the value of the [IpAddress](microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder-ipaddress.md).

**Note**  
This element does not appear in the **Properties** pane of Windows System Image Manager (Windows SIM) until you add [IpAddress](microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder-ipaddress.md) to the answer file.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Value</em></p></td>
<td><p>Specifies the value of the <a href="microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder-ipaddress.md" data-raw-source="[IpAddress](microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder-ipaddress.md)">IpAddress</a>. <em>Value</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-DNS-Client](microsoft-windows-dns-client.md) | [Interfaces](microsoft-windows-dns-client-interfaces.md) | [Interface](microsoft-windows-dns-client-interfaces-interface.md) | [DNSServerSearchOrder](microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder.md) | [IpAddress](microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder-ipaddress.md) | **Value**

## Valid Configuration Passes


specialize

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-DNS-Client](microsoft-windows-dns-client.md).

## XML Example


The following XML output shows a DNS domain configuration for Fabrikam.

```
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


[IpAddress](microsoft-windows-dns-client-interfaces-interface-dnsserversearchorder-ipaddress.md)

 

 







