---
title: NetworkMask
description: NetworkMask
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 81943f38-83b7-4438-8f04-7248b934253f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# NetworkMask


`NetworkMask` specifies the subnet mask for the virtual IP address. This is a required setting.

**Note**  
To enable this Network Load Balancing setting, the NetworkLoadBalancingFullServer package must be enabled in the Windows image you are installing. To do this, use Windows System Image Manager to add the Microsoft-Windows-Foundation-Package to your answer file, and then configure the NetworkLoadBalancingFullServer package to enable it. For more information about adding and configuring packages, see the [Windows Assessment and Deployment (Windows ADK) Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587).



## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>NetworkMask</em></p></td>
<td><p>Specifies the subnet mask for the virtual IP address.</p>
<div class="alert">
<strong>Note</strong><br/><p>This setting should not be used if the IP address is an IPv6 address.</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | [VirtualIpAddresses](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses.md) | [IpAddress](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses-ipaddress.md) | **NetworkMask**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following XML output specifies the subnet mask for the virtual IP address.

```
<NetworkMask>255.255.255.0</NetworkMask>
```

## Related topics


[IpAddress](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses-ipaddress.md)











