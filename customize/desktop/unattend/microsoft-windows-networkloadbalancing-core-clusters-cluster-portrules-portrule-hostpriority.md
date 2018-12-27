---
title: HostPriority
description: HostPriority
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 541e9461-3b8c-4b65-8d44-6dbe07f5116f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# HostPriority


`HostPriority` specifies the host's unique priority ID in the Network Load Balancing cluster. This is a required setting.

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
<td><p><em>HostPriority</em></p></td>
<td><p>Specifies the host&#39;s unique priority ID in the Network Load Balancing cluster. The default value is <strong>1</strong>.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | [Portrules](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules.md) | [Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md) | **HostPriority**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following XML output specifies the host's unique priority ID in the Network Load Balancing cluster.

```
<HostPriority>1</HostPriority>
```

## Related topics


[Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md)

 

 







