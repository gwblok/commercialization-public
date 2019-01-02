---
title: Portrule
description: Portrule
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 59ce39b3-5516-4cea-8eae-35baba20e33f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Portrule

`Portrule` specifies details about a port rule used for the cluster, including its name, virtual IP address, protocol, mode, and so on.

> [!Note]
> To enable this Network Load Balancing setting, the NetworkLoadBalancingFullServer package must be enabled in the Windows image you are installing. To do this, use Windows System Image Manager to add the Microsoft-Windows-Foundation-Package to your answer file, and then configure the NetworkLoadBalancingFullServer package to enable it. For more information about adding and configuring packages, see the [Windows Assessment and Deployment (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [ClientAffinity](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-clientaffinity.md) | Specifies how network multiple requests are directed in a cluster. |
| [EndPort](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-endport.md) | Specifies the end port used by the port rule. |
| [EqualLoad](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-equalload.md) | Specifies details about the equal load for the port rule. |
| [HostPriority](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-hostpriority.md) | Specifies the host priority for the port rule. |
| [Key](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-key.md) | Specifies the name of the port rule. |
| [LoadWeight](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-loadweight.md) | Specifies the load weight of the port rule. |
| [Mode](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-mode.md) | Specifies the mode of the port rule. |
| [Protocol](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-protocol.md) | Specifies the protocol used by the port rule. |
| [StartPort](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-startport.md) | Specifies the start port used by the port rule. |
| [Timeout](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-timeout.md) | Specifies the number of seconds for which the client affinity would be preserved across configuration changes in a cluster. |
| [VirtualIpAddress](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-virtualipaddress.md) | Specifies the virtual IP address of the port rule. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | [Portrules](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules.md) | **Portrule**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md).

## XML Example

The following XML output shows how to configure a port rule for a cluster

```XML
<Portrule wcm:keyValue="Portrule2">
   <VirtualIpAddress>10.100.0.223</VirtualIpAddress>
   <Protocol>Both</Protocol>
   <StartPort>80</StartPort>
   <EndPort>80</EndPort>
   <Mode>MultipleHost</Mode>
   <LoadWeight>100</LoadWeight>
   <ClientAffinity>Single</ClientAffinity>
</Portrule>
```

## Related topics

[Portrules](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules.md)
