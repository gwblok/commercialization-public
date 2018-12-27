---
title: Portrules
description: Portrules
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ae3cc863-84dc-4e6c-a61a-998ef63fcd31
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Portrules

`Portrules` specifies details about the port rules used for the cluster, including a port rule’s name, virtual IP address, protocol, mode, and so on.

> [!Note]
> To enable this Network Load Balancing setting, the NetworkLoadBalancingFullServer package must be enabled in the Windows image you are installing. To do this, use Windows System Image Manager to add the Microsoft-Windows-Foundation-Package to your answer file, and then configure the NetworkLoadBalancingFullServer package to enable it. For more information about adding and configuring packages, see the [Windows Assessment and Deployment (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587).

## Child Element

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md) | Specifies details about a port rule used for a cluster, such as its name, IP address, protocol, mode, and so on. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | **Portrules**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md).

## XML Example

The following XML output shows how to specify details about the port rules used for the cluster.

```XML
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
```

## Related topics

[Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md)
