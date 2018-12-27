---
title: DedicatedIpAddresses
description: DedicatedIpAddresses
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1f7114b9-9327-4f41-a68d-a51d4b9205de
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# DedicatedIpAddresses

`DedicatedIpAddresses` specifies the host's unique IP addresses. This is a required setting.

> [!Note]
> To enable this Network Load Balancing setting, the NetworkLoadBalancingFullServer package must be enabled in the Windows image you are installing. To do this, use Windows System Image Manager to add the Microsoft-Windows-Foundation-Package to your answer file, and then configure the NetworkLoadBalancingFullServer package to enable it. For more information about adding and configuring packages, see the [Windows Assessment and Deployment (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587).

## Child Element

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [IpAddress](microsoft-windows-networkloadbalancing-core-clusters-cluster-dedicatedipaddresses-ipaddress.md) | Specifies details about a host's unique IP address. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | **DedicatedIpAddresses**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-NetworkLoadBalancing-Core](microsoft-windows-networkloadbalancing-core.md).

## XML Example

The following XML output specifies a host's unique IP address.

```XML
<DedicatedIpAddresses>
   <IpAddress wcm:keyValue="Ip1">
      <IpAddress>10.192.45.1</IpAddress>
      <NetworkMask>255.255.255.0</NetworkMask>
   </IpAddress>
   <IpAddress wcm:keyValue="Ip2">
      <IpAddress>fe80::204:23ff:feb9:1111</IpAddress>
   </IpAddress>
</DedicatedIpAddresses>
```

## Related topics

[Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md)
