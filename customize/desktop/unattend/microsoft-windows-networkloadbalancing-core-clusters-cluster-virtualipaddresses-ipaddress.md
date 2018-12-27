---
title: IpAddress
description: IpAddress
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 765b659c-d699-4e03-aa56-9d5ab028b85f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# IpAddress

`IpAddress` specifies details about a cluster's virtual IP address, not associated with the cluster. At least one IP Address setting must be specified.

> [!Note]
> To enable this Network Load Balancing setting, the NetworkLoadBalancingFullServer package must be enabled in the Windows image you are installing. To do this, use Windows System Image Manager to add the Microsoft-Windows-Foundation-Package to your answer file, and then configure the NetworkLoadBalancingFullServer package to enable it. For more information about adding and configuring packages, see the [Windows Assessment and Deployment (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Key](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses-ipaddress-key.md) | Specifies the name of the virtual IP address. |
| [IpAddress](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses-ipaddress-ipaddress.md) | Specifies the IP address for the cluster's virtual IP address. |
| [NetworkMask](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses-ipaddress-networkmask.md) | Specifies the network mask for the cluster's virtual IP address. |

> [!Note]
> The `Key` XML attribute does not appear in the <strong>Properties</strong> pane of Windows System Image Manager (Windows SIM) until you add this IP Address to the answer file.

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | [VirtualIpAddresses](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses.md) | **IPAddress**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md).

## XML Example

The following XML output specifies details about the cluster's virtual IP address.

```XML
<IpAddress wcm:keyValue="Ip1">
   <IpAddress>207.46.197.32</IpAddress>
   <NetworkMask>255.255.255.0</NetworkMask>
</IpAddress>
```

## Related topics

[VirtualIpAddresses](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses.md)
