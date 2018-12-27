---
title: Interfaces
description: Interfaces
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d84ed504-c707-47ac-8087-0e1b0229d6ce
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Interfaces

`Interfaces` specifies details about the TCP/IP interface settings.

TCP/IP settings can be divided into two primary groups—global settings and interface settings. Global settings apply to the protocols as a whole and are applied across all network interfaces. Interface settings are specific to a particular network interface.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Interface](microsoft-windows-tcpip-interfaces-interface.md) | Contains settings for the TCP/IP interface. |

## Valid Configuration Passes

specialize

windowsPE

## Parent Hierarchy

[Microsoft-Windows-TCPIP](microsoft-windows-tcpip.md) | **Interfaces**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-TCPIP](microsoft-windows-tcpip.md).

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

[Microsoft-Windows-TCPIP](microsoft-windows-tcpip.md)
