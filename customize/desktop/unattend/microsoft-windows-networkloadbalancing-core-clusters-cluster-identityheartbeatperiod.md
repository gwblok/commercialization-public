---
title: IdentityHeartbeatPeriod
description: IdentityHeartbeatPeriod
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6b7468f0-4cbd-43ae-b39f-d8b9bc128611
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# IdentityHeartbeatPeriod


`IdentityHeartbeatPeriod` specifies the recurrence interval for transmitting identity heartbeats between the Network Load Balancing cluster hosts.

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
<td><p><em>IdentityHeartbeatPeriod</em></p></td>
<td><p>Specifies the recurrence interval, in milliseconds, for transmitting identity heartbeats between the Network Load Balancing cluster hosts. The default value and the minimum acceptable value is 10000 milliseconds (10 seconds).</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | **IdentityHeartbeatPeriod**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following XML output specifies the interval for transmitting identity heartbeats between the Network Load Balancing cluster is 2 seconds.

```
<IdentityHeartbeatPeriod>2000</IdentityHeartbeatPeriod>
```

## Related topics


[Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md)

 

 







