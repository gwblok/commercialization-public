---
title: InitialHostState
description: InitialHostState
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e77afb88-ccf8-4702-86c1-a781a5afe02b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# InitialHostState


`InitialHostState` specifies the initial host state for the cluster.

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
<td><p><strong>Stopped</strong></p></td>
<td><p>Specifies that the initial state of the host operating system for the cluster is stopped.</p></td>
</tr>
<tr class="even">
<td><p><strong>Suspended</strong></p></td>
<td><p>Specifies that the initial state of the host is suspended when the operating system is started.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Started</strong></p></td>
<td><p>Specifies that the host will immediately join the cluster when the operating system is started.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | **InitialHostState**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following sample XML output shows how to specify that the host will immediately join the cluster when the operating system is started.

```
<InitialHostState>Started</InitialHostState>
```

## Related topics


[Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md)

 

 







