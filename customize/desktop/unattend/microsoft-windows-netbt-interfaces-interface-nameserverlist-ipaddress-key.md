---
title: Key
description: Key
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0cc167aa-234b-4339-80fb-22ed80af7801
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Key


`Key` specifies a unique key for [IpAddress](microsoft-windows-netbt-interfaces-interface-nameserverlist-ipaddress.md). Name-server priority is based on the key of the IP address, with higher priority given to lower keys (lexicographically).

**Note**  
-   This element does not appear in the **Properties** pane of Windows System Image Manager (Windows SIM) until you add [IpAddress](microsoft-windows-netbt-interfaces-interface-nameserverlist-ipaddress.md) to the answer file.

-   The value for `Key` is added to the answer file as an attribute of the [IpAddress](microsoft-windows-netbt-interfaces-interface-nameserverlist-ipaddress.md) element. The attribute `wcm:keyValue` is used to identify each unique IP address. For example, you can specify three different IP addresses by using the Key values of **IpAddress1**, **IpAddress2**, and **IpAddress3**.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Key</em></p></td>
<td><p>Specifies a unique key for the IP address. <em>Key</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-netbt-](microsoft-windows-netbt.md) | [Interfaces](microsoft-windows-netbt-interfaces.md) | [Interface](microsoft-windows-netbt-interfaces-interface.md) | [NameServerList](microsoft-windows-netbt-interfaces-interface-nameserverlist.md) | [IpAddress](microsoft-windows-netbt-interfaces-interface-nameserverlist-ipaddress.md) | **Key**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-netbt-](microsoft-windows-netbt.md).

## XML Example


The following XML output shows how to configure microsoft-windows-netbt-.

```
<Interfaces>

 <Interface wcm:action="add">
      <NameServerList>
         <IpAddress wcm:action="add" wcm:keyValue="IpAddress1">123.45.67.89</IpAddress>
         <IpAddress wcm:action="add" wcm:keyValue="IpAddress2">56.78.90.123</IpAddress>
       </NameServerList>
       <NetbiosOptions>2</NetbiosOptions>
       <Identifier>Local Area Connection</Identifier>
   </Interface>
</Interfaces>
```

## Related topics


[IpAddress](microsoft-windows-netbt-interfaces-interface-nameserverlist-ipaddress.md)

 

 







