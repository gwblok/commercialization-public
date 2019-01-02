---
title: IpAddress
description: IpAddress
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e844f577-a3b6-4295-8fab-1965c77718c0
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# IpAddress

`IpAddress` specifies details about a host's unique IP address that is used for network traffic not associated with the cluster. At least one `IpAddress` setting must be specified.

## Child Element

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Key](microsoft-windows-networkloadbalancing-core-clusters-cluster-dedicatedipaddresses-ipaddress-key.md) | Specifies the name of the host's unique IP address. |
| [IpAddress](microsoft-windows-networkloadbalancing-core-clusters-cluster-dedicatedipaddresses-ipaddress-ipaddress.md) | Specifies the host's unique IP address. |
| [NetworkMask](microsoft-windows-networkloadbalancing-core-clusters-cluster-dedicatedipaddresses-ipaddress-networkmask.md) | Specifies the network mask for the host's unique IP address. |

> [!Note]
> The `Key` XML attribute does not appear in the <strong>Properties</strong> pane of Windows System Image Manager (Windows SIM) until you add <code>IpAddress</code> to the answer file.</p>

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | [DedicatedIpAddresses](microsoft-windows-networkloadbalancing-core-clusters-cluster-dedicatedipaddresses.md) | **IpAddress**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md).

## XML Example

The following XML output specifies a host's unique IP address.

```XML
<IpAddress wcm:keyValue="Ip1>
   <IpAddress>10.192.45.1</IpAddress>
   <NetworkMask>255.255.255.0</NetworkMask>
</IpAddress>
```

## Related topics

[DedicatedIpAddresses](microsoft-windows-networkloadbalancing-core-clusters-cluster-dedicatedipaddresses.md)
