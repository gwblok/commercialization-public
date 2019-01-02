---
title: NextHopAddress
description: NextHopAddress
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 544257a4-95a0-49a8-9a69-8dbac5994413
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# NextHopAddress


`NextHopAddress` specifies the IP address of the next hop in the [Route](microsoft-windows-tcpip-interfaces-interface-routes-route.md).

`NextHopAddress` can also be used to specify the default gateway in network configuration.

The settings under [Route](http://go.microsoft.com/fwlink/?LinkId=254767) must be added in the following order: [Identifier](http://go.microsoft.com/fwlink/?LinkId=224315), [Metric](http://go.microsoft.com/fwlink/?LinkId=224320), [NextHopAddress](http://go.microsoft.com/fwlink/?LinkId=224322), and then [Prefix](http://go.microsoft.com/fwlink/?LinkId=224326). After saving your Unattend file in Windows SIM, verify in the XML file that the output is shown in the correct order, as shown in the XML example below.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Nexthopaddress</em></p></td>
<td><p>Specifies the IP address of the next hop in the <a href="microsoft-windows-tcpip-interfaces-interface-routes-route.md" data-raw-source="[Route](microsoft-windows-tcpip-interfaces-interface-routes-route.md)">Route</a>. <em>Nexthopaddress</em> is a string with a maximum length of 45 characters.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

windowsPE

## Parent Hierarchy


[Microsoft-Windows-TCPIP](microsoft-windows-tcpip.md) | [Interfaces](microsoft-windows-tcpip-interfaces.md) | [Interface](microsoft-windows-tcpip-interfaces-interface.md) | [Routes](microsoft-windows-tcpip-interfaces-interface-routes.md) | [Route](microsoft-windows-tcpip-interfaces-interface-routes-route.md) | **NextHopAddress**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-TCPIP](microsoft-windows-tcpip.md).

## XML Example


The following XML output shows how to configure TCPIP.

```
<component name="Microsoft-Windows-TCPIP" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <Interfaces>
   <!-- Add static IP address (192.168.0.1/24, ffff:1::3/48) & route (12.34.0.0/16) to interface with identifier "Ethernet 1" -->      <Interface wcm:action="add">
         <Ipv4Settings>
            <DhcpEnabled>true</DhcpEnabled> 
            <Metric>20</Metric> 
            <RouterDiscoveryEnabled>false</RouterDiscoveryEnabled> 
         </Ipv4Settings>
         <Ipv6Settings>
            <DhcpEnabled>false</DhcpEnabled> 
            <Metric>30</Metric> 
            <RouterDiscoveryEnabled>true</RouterDiscoveryEnabled> 
         </Ipv6Settings>
      <Identifier>Ethernet 1</Identifier>
         <UnicastIpAddresses>
           <IpAddress wcm:action="add" wcm:keyValue="1">192.168.0.1/24</IpAddress>
           <IpAddress wcm:action="add" wcm:keyValue="2">ffff:1::3/48</IpAddress>
         </UnicastIpAddresses>
         <Routes>
            <Route wcm:action="add">
               <Identifier>1</Identifier> 
               <Metric>10</Metric> 
               <NextHopAddress>12.34.0.0</NextHopAddress> 
               <Prefix>16</Prefix> 
            </Route>
            <Route wcm:action="add">
               <Identifier>10</Identifier> 
               <Metric>29</Metric> 
               <NextHopAddress>12.34.56.0</NextHopAddress> 
               <Prefix>24</Prefix> 
            </Route>
         </Routes>
      </Interface>
      <Interface wcm:action="add">
         <Ipv4Settings>
            <DhcpEnabled>true</DhcpEnabled> 
            <Metric>20</Metric> 
            <RouterDiscoveryEnabled>false</RouterDiscoveryEnabled> 
         </Ipv4Settings>
         <Ipv6Settings>
            <DhcpEnabled>false</DhcpEnabled> 
            <Metric>10</Metric> 
            <RouterDiscoveryEnabled>true</RouterDiscoveryEnabled> 
         </Ipv6Settings>
         <Identifier>Local Area Connection</Identifier> 
         <UnicastIpAddresses>
            <IpAddress wcm:action="add" wcm:keyValue="1">123.45.67.8</IpAddress> 
            </UnicastIpAddresses>
         <Routes>
            <Route wcm:action="add">
               <Identifier>1</Identifier> 
               <Metric>10</Metric> 
               <NextHopAddress>12.34.0.0</NextHopAddress> 
               <Prefix>16</Prefix> 
            </Route>
         </Routes>
      </Interface>
   </Interfaces>
</component>
<Interfaces>
   <Interface wcm:action="add">
      <Ipv4Settings>
         <DhcpEnabled>true</DhcpEnabled> 
         <Metric>20</Metric> 
         <RouterDiscoveryEnabled>false</RouterDiscoveryEnabled> 
      </Ipv4Settings>
      <Ipv6Settings>
         <DhcpEnabled>false</DhcpEnabled> 
         <Metric>30</Metric> 
         <RouterDiscoveryEnabled>true</RouterDiscoveryEnabled> 
      </Ipv6Settings>
      <Identifier>123</Identifier>
      <UnicastIpAddresses>
        <IpAddress wcm:action="add" wcm:keyValue="1">192.168.0.1/24</IpAddress>
        <IpAddress wcm:action="add" wcm:keyValue="2">ffff:1::3/48</IpAddress>
      </UnicastIpAddresses>
      <Routes>
         <Route wcm:action="add">
            <Identifier>1</Identifier> 
            <Metric>10</Metric> 
            <NextHopAddress>12.34.0.0</NextHopAddress> 
            <Prefix>16</Prefix> 
         </Route>
         <Route wcm:action="add">
            <Identifier>10</Identifier> 
            <Metric>29</Metric> 
            <NextHopAddress>12.34.56.0</NextHopAddress> 
            <Prefix>24</Prefix> 
         </Route>
      </Routes>
   </Interface>
   <Interface wcm:action="add">
      <Ipv4Settings>
         <DhcpEnabled>true</DhcpEnabled> 
         <Metric>20</Metric> 
         <RouterDiscoveryEnabled>false</RouterDiscoveryEnabled> 
      </Ipv4Settings>
      <Ipv6Settings>
         <DhcpEnabled>false</DhcpEnabled> 
         <Metric>10</Metric> 
         <RouterDiscoveryEnabled>true</RouterDiscoveryEnabled> 
      </Ipv6Settings>
      <Identifier>456</Identifier> 
      <UnicastIpAddresses>
         <IpAddress wcm:action="add" wcm:keyValue="1">123.45.67.8</IpAddress> 
         </UnicastIpAddresses>
      <Routes>
         <Route wcm:action="add">
            <Identifier>1</Identifier> 
            <Metric>10</Metric> 
            <NextHopAddress>12.34.0.0</NextHopAddress> 
            <Prefix>16</Prefix> 
         </Route>
      </Routes>
   </Interface>
</Interfaces>
```

## Related topics


[Route](microsoft-windows-tcpip-interfaces-interface-routes-route.md)

 

 







