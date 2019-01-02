---
title: EqualLoad
description: EqualLoad
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b8f7fea3-6c1d-4164-a9c0-813d85055fad
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# EqualLoad


`EqualLoad` specifies whether the load is distributed equally across all nodes.

**Note**  
To enable this Network Load Balancing setting, the NetworkLoadBalancingFullServer package must be enabled in the Windows image you are installing. To do this, use Windows System Image Manager to add the Microsoft-Windows-Foundation-Package to your answer file, and then configure the NetworkLoadBalancingFullServer package to enable it. For more information about adding and configuring packages, see the [Windows Assessment and Deployment (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587).

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the distribution of the load is uniform for all nodes in the cluster. A default load weight of <strong>50</strong> is assigned to each node in the cluster. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the number specified in the <a href="microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-loadweight.md" data-raw-source="[LoadWeight](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-loadweight.md)">LoadWeight</a> setting is used to increase or decrease the load relative to other nodes in the cluster.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | [Portrules](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules.md) | [Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md) | **EqualLoad**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following XML output shows how to specify that the number specified in the [LoadWeight](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-loadweight.md) setting is used to increase or decrease the load relative to other nodes in the cluster.

```
<EqualLoad>false</EqualLoad>
<LoadWeight>100</LoadWeight>
```

The following XML output shows how to specify that the distribution of the load is uniform for all nodes in the cluster.

```
<EqualLoad>true</EqualLoad>
```

## Related topics


[Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md)

 

 







