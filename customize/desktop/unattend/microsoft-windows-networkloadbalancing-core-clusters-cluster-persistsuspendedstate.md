---
title: PersistSuspendedState
description: PersistSuspendedState
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 472bbc0b-4db2-4eb1-af51-4a6c43c321e4
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PersistSuspendedState


`PersistSuspendedState` specifies whether a host that is shut down while in a suspended state will remain suspended when Windows is started.

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
<td><p><strong>false</strong></p></td>
<td><p>Specifies that a host that is shut down while in a suspended state will not remain suspended when Windows is started.</p></td>
</tr>
<tr class="even">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that a host that is shut down while in a suspended state will remain suspended when Windows is started. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | **PersistedSuspendedState**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following XML output specifies that a host that is shut down while in a suspended state will remain suspended when Windows is started.

```
<PersistSuspendedState>false</PersistSuspendedState>
```

## Related topics


[Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md)

 

 







