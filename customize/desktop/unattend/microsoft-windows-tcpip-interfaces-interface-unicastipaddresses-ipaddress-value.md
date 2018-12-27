---
title: Value
description: Value
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ec2f6d75-998c-4b09-83c6-457a681fea3d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Value


`Value` specifies the value of the [IpAddress](microsoft-windows-tcpip-interfaces-interface-unicastipaddresses-ipaddress.md).

It can also optionally specify a routing prefix length, which is often expressed as a subnet mask. The *routing prefix length* refers to the number of leading bits in the IP address. A *subnet mask* is a bit mask covering the number of bits used in the prefix.

If the routing prefix length is not defined, the default routing prefix length will be used, based on the class of the IP address.

**Default routing prefix lengths and subnet masks for IPv4 addresses**

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th>Class</th>
<th>Start</th>
<th>End</th>
<th>Default routing prefix length</th>
<th>Default subnet mask in dotted decimal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A</p></td>
<td><p>0.0.0.0</p></td>
<td><p>127.255.255.255</p></td>
<td><p>8</p></td>
<td><p>255.0.0.0</p></td>
</tr>
<tr class="even">
<td><p>B</p></td>
<td><p>128.0.0.0</p></td>
<td><p>191.255.255.255</p></td>
<td><p>16</p></td>
<td><p>255.255.0.0</p></td>
</tr>
<tr class="odd">
<td><p>C</p></td>
<td><p>192.0.0.0</p></td>
<td><p>223.255.255.255</p></td>
<td><p>24</p></td>
<td><p>255.255.255.0</p></td>
</tr>
<tr class="even">
<td><p>D</p></td>
<td><p>224.0.0.0</p></td>
<td><p>239.255.255.255</p></td>
<td><p>Multicasting</p></td>
<td><p>Multicasting</p></td>
</tr>
<tr class="odd">
<td><p>E</p></td>
<td><p>240.0.0.0</p></td>
<td><p>255.255.255.254</p></td>
<td><p>Reserved</p></td>
<td><p>Reserved</p></td>
</tr>
</tbody>
</table>

 

**Note**  
This element does not appear in the **Properties** pane of Windows System Image Manager (Windows SIM) until you add [IpAddress](microsoft-windows-tcpip-interfaces-interface-unicastipaddresses-ipaddress.md) to the unattended installation answer file.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Value</em></p></td>
<td><p>Specifies the value of the IP Address, and routing prefix length. <em>Value</em> is a string.</p>
<p>To use the default routing prefix length, use the format: <em>&lt;IP_Address&gt;</em>. <em>&lt;IP_Address&gt;</em> can be any valid IPv4 or IPv6 address.</p>
<p>To define a routing prefix length, use the format: <em>&lt;IP_Address&gt;/&lt;Routing_Prefix_Length&gt;</em>. For IPv4 addresses, <em>&lt;Routing_Prefix_Length&gt;</em> can be any value between 0 and 32. For IPv6 addresses, <em>&lt;Routing_Prefix_Length&gt;</em> can be any value between 0 and 64.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

windowsPE

## Parent Hierarchy


[Microsoft-Windows-TCPIP](microsoft-windows-tcpip.md) | [Interfaces](microsoft-windows-tcpip-interfaces.md) | [Interface](microsoft-windows-tcpip-interfaces-interface.md) | [UnicastIpAddresses](microsoft-windows-tcpip-interfaces-interface-unicastipaddresses.md) | [IpAddress](microsoft-windows-tcpip-interfaces-interface-unicastipaddresses-ipaddress.md) | **Value**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-TCPIP](microsoft-windows-tcpip.md).

## XML Example


The following XML output shows how to configure two static IP addresses. In this example:

-   The IPv4 address is set to 192.168.1.0, with a routing prefix length of 25. This defines the subnet mask as 255.255.255.128.

-   The IPv6 address is set to ffff:1::3, with a routing prefix length of 48. This defines the subnet mask as ffff:ffff:ffff:0000:0000:0000:0000:0000.

```
      <UnicastIpAddresses>
         <IpAddress wcm:action="add" wcm:keyValue="1">192.168.0.1/25</IpAddress> 
         <IpAddress wcm:action="add" wcm:keyValue="2">ffff:1::3/48</IpAddress> 
      </UnicastIpAddresses>
```

The following XML output shows how to configure a single IP address. In this example, the IP address is set to 10.168.1.0. This is an IPv4 Class A address. Windows uses the default subnet mask of 255.0.0.0.

```
      <UnicastIpAddresses>
         <IpAddress wcm:action="add" wcm:keyValue="1">10.168.1.0</IpAddress> 
      </UnicastIpAddresses>
```

The following XML output shows how to configure a single TCP/IP address. In this example, the IP address is set to 160.168.1.0. This is an IPv4 Class B address. Windows uses the default subnet mask of 255.255.0.0.

```
      <UnicastIpAddresses>
         <IpAddress wcm:action="add" wcm:keyValue="1">160.168.1.0</IpAddress> 
      </UnicastIpAddresses>
```

## Related topics


[IpAddress](microsoft-windows-tcpip-interfaces-interface-unicastipaddresses-ipaddress.md)

 

 







