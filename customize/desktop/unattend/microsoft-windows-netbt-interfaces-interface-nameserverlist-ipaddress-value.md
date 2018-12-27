---
title: Value
description: Value
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e9c4df7a-b8aa-45ab-a090-811b72109889
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Value


`Value` specifies the value of [IpAddress](microsoft-windows-netbt-interfaces-interface-nameserverlist-ipaddress.md).

**Note**  
This element does not appear in the **Properties** pane of Windows System Image Manager (Windows SIM) until you add [IpAddress](microsoft-windows-netbt-interfaces-interface-nameserverlist-ipaddress.md) to the answer file.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Value</em></p></td>
<td><p>Specifies the value of the IP address. <em>Value</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-netbt-](microsoft-windows-netbt.md) | [Interfaces](microsoft-windows-netbt-interfaces.md) | [Interface](microsoft-windows-netbt-interfaces-interface.md) | [NameServerList](microsoft-windows-netbt-interfaces-interface-nameserverlist.md) | [IpAddress](microsoft-windows-netbt-interfaces-interface-nameserverlist-ipaddress.md) | **Value**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-netbt-](microsoft-windows-netbt.md).

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

 

 







