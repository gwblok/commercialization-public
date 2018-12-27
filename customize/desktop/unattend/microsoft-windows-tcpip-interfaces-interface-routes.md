---
title: Routes
description: Routes
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3b809cb8-c010-4fd7-87b8-b83f788be93a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Routes

`Routes` contains entries that specify IPv4 or IPv6 routes.

> [!Note]
> The settings in [Interface](microsoft-windows-tcpip-interfaces-interface.md) must be added in the following order: [Ipv4Settings](microsoft-windows-tcpip-interfaces-interface-ipv4settings.md), [Ipv6Settings](microsoft-windows-tcpip-interfaces-interface-ipv6settings.md), [Identifier](microsoft-windows-tcpip-interfaces-interface-identifier.md), [UnicastIpAddresses](microsoft-windows-tcpip-interfaces-interface-unicastipaddresses.md), and then Routes. After saving your Unattend file in Windows SIM, verify in the XML file that the output is shown in the correct order, as shown in the XML example below.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Route](microsoft-windows-tcpip-interfaces-interface-routes-route.md) | Specifies an individual IPv4 or IPv6 route. |

## Valid Configuration Passes

specialize

windowsPE

## Parent Hierarchy

[Microsoft-Windows-TCPIP](microsoft-windows-tcpip.md) | [Interfaces](microsoft-windows-tcpip-interfaces.md) | [Interface](microsoft-windows-tcpip-interfaces-interface.md) | **Routes**

## Applies To

For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-TCPIP](microsoft-windows-tcpip.md).

## XML Example

The following XML output shows how to configure TCPIP.

```XML
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
```

## Related topics

[Interface](microsoft-windows-tcpip-interfaces-interface.md)
