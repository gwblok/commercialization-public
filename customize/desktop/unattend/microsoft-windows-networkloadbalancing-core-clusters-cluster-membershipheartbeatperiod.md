---
title: MembershipHeartbeatPeriod
description: MembershipHeartbeatPeriod
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 672d839b-9d80-481d-8b43-fb3d75e79c54
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# MembershipHeartbeatPeriod


`MembershipHeartbeatPeriod` specifies in milliseconds a period between sending Network Load Balancing cluster heartbeat messages.

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
<td><p><em>MembershipHeartbeatPeriod</em></p></td>
<td><p>Specifies in milliseconds a period between sending Network Load Balancing cluster heartbeat messages. The default setting is <strong>1000</strong>.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | **MembershipHeartbeatPeriod**

## Applies To


For the list of a supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following XML output shows how to set the period between sending Network Load Balancing cluster heartbeat messages to two seconds.

```
<MembershipHeartbeatPeriod>2000</MembershipHeartbeatPeriod>
```

## Related topics


[Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md)

 

 







