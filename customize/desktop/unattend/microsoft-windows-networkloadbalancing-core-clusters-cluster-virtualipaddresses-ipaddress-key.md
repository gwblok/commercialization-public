---
title: Key
description: Key
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e8fc6113-3a14-47f0-8ab4-2baa1a23dfda
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Key


`Key` specifies the name of the virtual IP address. The name is specified as an attribute in the IP address.

**Note**  
-   This XML attribute does not appear in the **Properties** pane of Windows System Image Manager (Windows SIM) until you add an [IpAddress](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses-ipaddress.md) to the answer file.

-   The value for `Key` is added to the answer file as an attribute of the [IpAddress](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses-ipaddress.md) element. The attribute `wcm:keyValue` is used to identify each unique virtual IP Address. For example, you can specify three different virtual IP addresses by using the `Key` value of **Ip1**, **Ip2**, and **Ip3**.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Key</em></p></td>
<td><p>Specifies the name of the virtual IP address.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md) | [Clusters](microsoft-windows-networkloadbalancing-core-clusters.md) | [Cluster](microsoft-windows-networkloadbalancing-core-clusters-cluster.md) | [VirtualIpAddresses](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses.md) | [IpAddress](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses-ipaddress.md) | **Key**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-networkloadbalancing-core-](microsoft-windows-networkloadbalancing-core.md).

## XML Example


The following XML output shows how to specify a virtual IP address by using the name "Ip1".

```
<IpAddress wcm:keyValue="Ip1">
   <IpAddress>10.192.45.1</IpAddress>
   <NetworkMask>255.255.255.0</NetworkMask>
</IpAddress>
```

## Related topics


[IpAddress](microsoft-windows-networkloadbalancing-core-clusters-cluster-virtualipaddresses-ipaddress.md)

 

 







