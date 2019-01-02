---
title: MembershipHeartbeatLossTolerance
description: MembershipHeartbeatLossTolerance
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 62d38c39-3fd5-4893-8657-9f6082284f93
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# MembershipHeartbeatLossTolerance


`MembershipHeartbeatLossTolerance` specifies the number of lost heartbeat messages before setup considers the Network Load Balancing cluster host to be inactive and initiates convergence.

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
<td><p><em>MembershipHeartbeatLossTolerance</em></p></td>
<td><p>Specifies the number of lost heartbeat messages before setup considers the Network Load Balancing cluster host to be inactive and initiates convergence. The default setting is <strong>5</strong>.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | **MembershipHeartbeatLossTolerance**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following XML output specifies that when five heartbeat messages are lost, setup considers the Network Load Balancing cluster host inactive and initiates convergence.

```
<MembershipHeartbeatLossTolerance>5</MembershipHeartbeatLossTolerance>
```

## Related topics


[Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md)

 

 







