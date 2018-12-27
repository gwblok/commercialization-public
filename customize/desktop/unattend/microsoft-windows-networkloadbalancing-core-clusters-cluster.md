---
title: Cluster
description: Cluster
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b9c7e245-6a44-4d7b-b435-41510d5e58fb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Cluster

`Cluster` contains the settings to specify details about a cluster, such as its interface, IP address, portrules, and so on.

> [!Note]
> To enable this Network Load Balancing setting, the NetworkLoadBalancingFullServer package must be enabled in the Windows image you are installing. To do this, use Windows System Image Manager to add the Microsoft-Windows-Foundation-Package to your answer file, and then configure the NetworkLoadBalancingFullServer package to enable it. For more information about adding and configuring packages, see the [Windows Assessment and Deployment (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
|[BDATeam](microsoft-windows-networkloadbalancing-core-clusters-cluster-bdateam.md)|Specifies details about a bidirectional affinity (BDA) team.|
|[ClusterIpAddress](microsoft-windows-networkloadbalancing-core-clusters-cluster-clusteripaddress.md)|Specifies the cluster primary IP address.|
|[ClusterIpToClusterMacEnabled](microsoft-windows-networkloadbalancing-core-clusters-cluster-clusteriptoclustermacenabled.md)|Specifies whether the cluster MAC address is automatically calculated from the primary cluster IP address.|
|[ClusterMacAddress](microsoft-windows-networkloadbalancing-core-clusters-cluster-clustermacaddress.md)|Specifies the cluster MAC address to be used when configuring a unicast cluster.|
|[ClusterMode](microsoft-windows-networkloadbalancing-core-clusters-cluster-clustermode.md)|Specifies the mode for the cluster.|
|[ClusterName](microsoft-windows-networkloadbalancing-core-clusters-cluster-clustername.md)|Specifies a full Internet name for the cluster.|
|[ClusterNetMask](microsoft-windows-networkloadbalancing-core-clusters-cluster-clusternetmask.md)|Specifies the subnet mask for the cluster IP address.|
|[DedicatedIpAddresses](microsoft-windows-networkloadbalancing-core-clusters-cluster-dedicatedipaddresses.md)|Specifies the host's unique IP addresses.|
|[HostIdentifier](microsoft-windows-networkloadbalancing-core-clusters-cluster-hostidentifier.md)|Specifies the host identifier used by this cluster.|
|[ICMPFilteringEnabled](microsoft-windows-networkloadbalancing-core-clusters-cluster-icmpfilteringenabled.md)|Specifies whether Internet Control Message Protocol (ICMP) filtering is enabled for the cluster.|
|[IdentityHeartbeatPeriod](microsoft-windows-networkloadbalancing-core-clusters-cluster-identityheartbeatperiod.md)|Specifies the recurrence interval for transmitting identity heartbeats between the NetworkLoadBalancing cluster hosts.|
|[InitialHostState](microsoft-windows-networkloadbalancing-core-clusters-cluster-initialhoststate.md)|Specifies the initial host state for the cluster.|
|[Interface](microsoft-windows-networkloadbalancing-core-clusters-cluster-interface.md)|Specifies the interface name to bind to network load balancing (NLB). This is a required setting.|
|[MaskSourceMacEnabled](microsoft-windows-networkloadbalancing-core-clusters-cluster-masksourcemacenabled.md)|Specifies whether source Media Access Control (MAC) address masking is used.|
|[MaximumConnectionDescriptors](microsoft-windows-networkloadbalancing-core-clusters-cluster-maximumconnectiondescriptors.md)|Specifies the maximum number of descriptors per allocation for the cluster.|
|[MembershipHeartbeatLossTolerance](microsoft-windows-networkloadbalancing-core-clusters-cluster-membershipheartbeatlosstolerance.md)|Specifies the number of lost heartbeat messages before Setup considers the Network Load Balancing cluster host inactive and initiates convergence.|
|[MembershipHeartbeatPeriod](microsoft-windows-networkloadbalancing-core-clusters-cluster-membershipheartbeatperiod.md)|Specifies a period between sending Network Load Balancing cluster heartbeat messages.|
|[MulticastSpoofEnabled](microsoft-windows-networkloadbalancing-core-clusters-cluster-multicastspoofenabled.md)|Specifies whether address resolution protocol (ARP) traffic should be spoofed.|
|[NetBTSupportEnabled](microsoft-windows-networkloadbalancing-core-clusters-cluster-netbtsupportenabled.md)|Specifies whether NetBT support is enabled for the cluster.|
|[PersistSuspendedState](microsoft-windows-networkloadbalancing-core-clusters-cluster-persistsuspendedstate.md)|Specifies whether a host that is shut down while in a suspended state will remain suspended when Windows is started.|
|[Portrules](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules.md)|Specifies details about the port rules that are used for the cluster, including a port rule's name, virtual IP address, protocol, mode, and so on.|
|[UnicastInterHostCommunicationSupportEnabled](microsoft-windows-networkloadbalancing-core-clusters-cluster-unicastinterhostcommunicationsupportenabled.md)|Specifies whether unicast, interhost communication support is enabled for the cluster.|
|[VirtualIpAddresses](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses.md)|Specifies the cluster’s virtual IP addresses.|


## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | **Cluster**

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md).

## XML Example

The following XML output shows how to specify details about a cluster.

```XML
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
      <ReverseHash>true</ReverseHash>
   </BDATeam>
</Cluster>
```

## Related topics

[Clusters](microsoft-windows-networkloadbalancing-core-clusters.md)
