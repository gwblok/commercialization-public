---
title: Key
description: Key
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8233cd59-b8b5-4791-818e-6ffa2ddd3801
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Key


`Key` specifies the name of the port rule used by the cluster. The name is specified as an attribute in the port rule.

**Note**  
-   This setting does not appear in the **Properties** pane of Windows System Image Manager (Windows SIM) until you add IPAddress to the answer file.

-   The value for `Key` is added to the answer file as an attribute of the [Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md) element. The attribute `wcm:keyValue` is used to identify each unique port rule. For example, you can specify three different port rules by using the `Key` values of **Portrule1**, **Portrule2**, and **Portrule3**.

-   To enable this Network Load Balancing setting, the NetworkLoadBalancingFullServer package must be enabled in the Windows image you are installing. To do this, use Windows System Image Manager to add the Microsoft-Windows-Foundation-Package to your answer file, and then configure the NetworkLoadBalancingFullServer package to enable it. For more information about adding and configuring packages, see the [Windows Assessment and Deployment (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587).

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Key</em></p></td>
<td><p>Specifies the name of the port rule.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | [Portrules](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules.md) | [Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md) | **Key**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following XML output shows how to specify the name of the port rule used by the cluster as "Portrule1".

```
<Portrule wcm:keyValue="Portrule1">
   <VirtualIpAddress>255.255.255.255</VirtualIpAddress>
   <Protocol>TCP</Protocol>
   <StartPort>0</StartPort>
   <EndPort>65535</EndPort>
   <Mode>MultipleHost</Mode>
   <EqualLoad>true</EqualLoad>
   <ClientAffinity>None</ClientAffinity>
</Portrule>
```

## Related topics


[Portrule](microsoft-windows-networkloadbalancing-core-clusters-cluster-portrules-portrule.md)

 

 







