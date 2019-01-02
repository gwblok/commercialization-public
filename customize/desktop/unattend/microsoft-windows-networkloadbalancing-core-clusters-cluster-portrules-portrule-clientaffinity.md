---
title: ClientAffinity
description: ClientAffinity
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ed40ad07-a5a8-435f-b4e8-eeafcc67d1ba
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ClientAffinity


`ClientAffinity` specifies how network multiple requests are directed in a cluster.

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
<td><p>Specifies that Network Load Balancing direct multiple requests from the same client IP address to the same cluster host. This is the default setting.</p></td>
</tr>
<tr class="even">
<td><p><strong>Network</strong></p></td>
<td><p>Specifies that Network Load Balancing direct multiple requests from the same TCP/IP Class C address range to the same cluster host.</p></td>
</tr>
<tr class="odd">
<td><p><strong>None</strong></p></td>
<td><p>Specifies that multiple connections from the same client IP address can be handled by different cluster hosts (no client affinity). Avoid using <strong>None</strong> when selecting <strong>UDP</strong> or <strong>Both</strong> for your protocol setting.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | [Portrules](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules.md) | [Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md) | **ClientAffinity**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following XML output shows how to specify that multiple connections from the same client IP address can be handled by different cluster hosts.

```
<ClientAffinity>None</ClientAffinity>
```

## Related topics


[Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md)

 

 







