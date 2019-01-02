---
title: Timeout
description: Timeout
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9b7852d4-5d0a-4f6d-81b9-b3f85486be0f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Timeout


The `Timeout` setting specifies the number of seconds for which the client affinity (either single or network) would be preserved across configuration changes in the Network Load Balancing cluster.

Client affinity is used to associate client requests to cluster hosts.

By default, all network requests are load-balanced across the cluster without respect to their source. Affinity is implemented by directing all client requests from the same IP address to the same cluster host.

When extended client affinity is specified, then after a network connection terminates, it retains ownership of a connection for a configurable amount of time. Requests coming in from the same client during the timeout period are guaranteed to be picked up by the same cluster host. After this time expires, the connection is released.

**Note**  
-   This setting will be applied only if the [ClientAffinity](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule-clientaffinity.md) setting is set to `Single` or `Network`.

-   To enable this Network Load Balancing setting, the NetworkLoadBalancingFullServer package must be enabled in the Windows image you are installing. To do this, use Windows System Image Manager to add the Microsoft-Windows-Foundation-Package to your answer file, and then configure the NetworkLoadBalancingFullServer package to enable it. For more information about adding and configuring packages, see the [Windows Assessment and Deployment (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587).

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Number_of_seconds</em></p></td>
<td><p>Specifies a number of seconds for extended client affinity. During this time, requests coming in from the same client are guaranteed to be picked up by the same cluster host.</p>
<p><em>Number_of_seconds</em> is an integer value.</p>
<p>The default value is 0, meaning extended affinity is not used. All network requests are load-balanced across the cluster without respect to their source.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | [Portrules](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules.md) | [Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md) | **Timeout**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following XML example shows how to set the network so that requests from the same client are guaranteed to be picked up by the same cluster host until a timeout period of 15 minutes expires.

```
<Timeout>900</Timeout>
```

## Related topics


[Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md)

 

 







