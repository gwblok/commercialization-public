---
title: ClusterMacAddress
description: ClusterMacAddress
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 39c0ffff-fcb4-4542-b005-ce000136c633
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ClusterMacAddress


`ClusterMacAddress` specifies the cluster MAC address to be used when configuring a unicast cluster. This MAC address will replace the adapter's physical MAC address.

**Note**  
To enable this Network Load Balancing setting, the NetworkLoadBalancingFullServer package must be enabled in the Windows image you are installing. To do this, use Windows System Image Manager to add the Microsoft-Windows-Foundation-Package to your answer file, and then configure the NetworkLoadBalancingFullServer package to enable it. For more information about adding and configuring packages, see the [Windows Assessment and Deployment (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587).



## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>ClusterMacAddress</em></p></td>
<td><p>Specifies the cluster MAC address be used when configuring a unicast cluster. This MAC address will replace the adapter&#39;s physical MAC address.</p>
<div class="alert">
<strong>Note</strong><br/><p>You must set <a href="microsoft-windows-networkloadbalancing-core-clusters-cluster-clusteriptoclustermacenabled.md" data-raw-source="[ClusterIpToClusterMacEnabled](microsoft-windows-networkloadbalancing-core-clusters-cluster-clusteriptoclustermacenabled.md)">ClusterIpToClusterMacEnabled</a> to <strong>False</strong> for this setting to work. If it is set to <strong>True</strong>, the cluster MAC address is automatically generated based on the cluster IP address.</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | **ClusterMacAddress**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following XML output shows how to specify a cluster MAC address.

```
<ClusterMacAddress>02-bf-01-02-03-04</ClusterMacAddress>
```

## Related topics


[Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md)











