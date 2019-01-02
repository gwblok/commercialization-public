---
title: Clusters
description: Clusters
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e4e00dcc-e259-4c5d-a61e-0a1e532f12b7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Clusters

`Clusters` contains the settings to specify details about clusters.

> [!Note]
> To enable this Network Load Balancing setting, the NetworkLoadBalancingFullServer package must be enabled in the Windows image you are installing. To do this, use Windows System Image Manager to add the Microsoft-Windows-Foundation-Package to your answer file, and then configure the NetworkLoadBalancingFullServer package to enable it. For more information about adding and configuring packages, see the [Windows Assessment and Deployment (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | Specifies details about a cluster, such as its interface, IP address, port rules, and so on. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md) | **Clusters**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md).

## XML Example

The following XML output for the `Clusters` setting shows how to set up a cluster for network load balancing.

```XML
<Clusters>
   <Cluster>
      <Interface>Local Area Connection 2</Interface>
      <ClusterIpAddress>10.100.0.234</ClusterIpAddress>
      <ClusterNetMask>255.255.255.0</ClusterNetMask>
      <VirtualIpAddresses>
         <IpAddress wcm:keyValue="Ip1">
            <IpAddress>10.192.45.1</IpAddress>
            <NetworkMask>255.255.255.0</NetworkMask>
         </IpAddress>
         <IpAddress wcm:keyValue="Ip2">
            <IpAddress>fe80::204:23ff:feb9:1111</IpAddress>
         </IpAddress>
      </VirtualIpAddresses>
      <Portrules>
         <Portrule wcm:keyValue="Portrule1">
            <VirtualIpAddress>255.255.255.255</VirtualIpAddress>
            <Protocol>TCP</Protocol>
            <StartPort>0</StartPort>
            <EndPort>65535</EndPort>
            <Mode>MultipleHost</Mode>
            <EqualLoad>true</EqualLoad>
            <ClientAffinity>None</ClientAffinity>
         </Portrule>
         <Portrule wcm:keyValue="Portrule2">
            <VirtualIpAddress>10.100.0.223</VirtualIpAddress>
            <Protocol>Both</Protocol>
            <StartPort>80</StartPort>
            <EndPort>80</EndPort>
            <Mode>MultipleHost</Mode>
            <LoadWeight>100</LoadWeight>
            <ClientAffinity>Single</ClientAffinity>
         </Portrule>
         <Portrule wcm:keyValue="Portrule3">
            <VirtualIpAddress>10.100.0.99</VirtualIpAddress>
            <Protocol>TCP</Protocol>
            <StartPort>23</StartPort>
            <EndPort>23</EndPort>
            <Mode>Disabled</Mode>
         </Portrule>
         <Portrule wcm:keyValue="Portrule4">
            <VirtualIpAddress>255.255.255.255</VirtualIpAddress>
            <Protocol>UDP</Protocol>
            <StartPort>25</StartPort>
            <EndPort>25</EndPort>
            <Mode>MultipleHost</Mode>
            <EqualLoad>true</EqualLoad>
            <ClientAffinity>Network</ClientAffinity>
         </Portrule>
         <Portrule wcm:keyValue="Portrule5">
            <VirtualIpAddress>10.100.0.223</VirtualIpAddress>
            <Protocol>TCP</Protocol>
            <StartPort>3389</StartPort>
            <EndPort>3389</EndPort>
            <Mode>SingleHost</Mode>
            <HostPriority>1</HostPriority>
         </Portrule>
      </Portrules>
      <DedicatedIpAddresses>
         <IpAddress wcm:keyValue="Ip1">
            <IpAddress>10.192.45.1</IpAddress>
            <NetworkMask>255.255.255.0</NetworkMask>
         </IpAddress>
         <IpAddress wcm:keyValue="Ip2">
            <IpAddress>fe80::204:23ff:feb9:1111</IpAddress>
         </IpAddress>
      </DedicatedIpAddresses>
      <HostIdentifier>6</HostIdentifier>
      <ClusterMacAddress>02-bf-01-02-03-04</ClusterMacAddress>
      <ClusterName>mycluster.domain.com</ClusterName>
      <ClusterMode>Multicast</ClusterMode>
      <InitialHostState>Started</InitialHostState>
      <PersistSuspendedState>false</PersistSuspendedState>
      <MembershipHeartbeatPeriod>1000</MembershipHeartbeatPeriod>
      <MembershipHeartbeatLossTolerance>5</MembershipHeartbeatLossTolerance>
      <IdentityHeartbeatPeriod>2000</IdentityHeartbeatPeriod>
      <MulticastSpoofEnabled>false</MulticastSpoofEnabled>
      <MaskSourceMacEnabled>true</MaskSourceMacEnabled>
      <ICMPFilteringEnabled>false</ICMPFilteringEnabled>
      <NetBTSupportEnabled>true</NetBTSupportEnabled>
      <ClusterIpToClusterMacEnabled>true</ClusterIpToClusterMacEnabled>
      <UnicastInterHostCommunicationSupportEnabled>true</UnicastInterHostCommunicationSupportEnabled>
      <MaximumConnectionDescriptors>512</MaximumConnectionDescriptors>
      <BDATeam>
         <Team>{BF967924-0DE6-11D0-A285-00AA003049E2}</Team>
         <Master>true</Master>
         <ReverseHash>false</ReverseHash>
      </BDATeam>
   </Cluster>
</Clusters>
```

## Related topics

[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md)
