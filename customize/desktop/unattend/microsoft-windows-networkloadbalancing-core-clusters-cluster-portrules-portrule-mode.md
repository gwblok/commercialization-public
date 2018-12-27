---
title: Mode
description: Mode
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 23a29798-fb04-4a51-adcd-4587fea9d255
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Mode


`Mode` specifies the mode of the port rule used by the cluster.

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
<td><p><strong>Single</strong></p></td>
<td><p>Specifies that network traffic for the associated port rule is handled by a single host in the cluster, according to the specified handling priority.</p></td>
</tr>
<tr class="even">
<td><p><strong>MultipleHost</strong></p></td>
<td><p>Specifies that multiple hosts in the cluster handle network traffic for the associated port rule.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Disabled</strong></p></td>
<td><p>Specifies that all network traffic for the associated port rule be blocked.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | [Portrules](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules.md) | [Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md) | **Mode**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following sample XML output shows how to specify that multiple hosts in the cluster handle network traffic for the associated port rule.

```
<Mode>MultipleHost</Mode>
```

## Related topics


[Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md)

 

 







