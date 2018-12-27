---
title: UseDomainNameDevolution
description: UseDomainNameDevolution
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 530294f6-d863-4a8e-a34e-9ed6cf92870b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# UseDomainNameDevolution


`UseDomainNameDevolution` specifies whether the name resolver uses domain-name devolution to resolve an unqualified query. For example, when a query with a single-label name is received, such as "Fabrikam", `UseDomainNameDevolution` specifies whether a domain is added to it to make it "Fabrikam.com".

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the name resolver uses domain-name devolution. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the name resolver does not use domain-name devolution.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-DNS-Client](microsoft-windows-dns-client.md) | **UseDomainNameDevolution**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-DNS-Client](microsoft-windows-dns-client.md).

## XML Example


The following XML output specifies a DNS domain configuration for Fabrikam.

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


[Microsoft-Windows-DNS-Client](microsoft-windows-dns-client.md)

 

 







