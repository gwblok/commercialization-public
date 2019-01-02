---
title: Identifier
description: Identifier
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4b9ba7ec-f231-4ab0-87b3-0f40d437cbed
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Identifier


`Identifier` specifies the interface to apply to other settings within [Interface](microsoft-windows-netbt-interfaces-interface.md). It can be expressed in one of the following ways:

-   As a string representation of an interface net locally unique identifier (NetLUID) (0x6000001000000)

-   As an interface alias (Local Area Connection)

-   As an interface MAC address (00-11-22-33-44-55)

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Identifier</em></p></td>
<td><p>Specifies the interface to apply to the other settings within the <a href="microsoft-windows-netbt-interfaces-interface.md" data-raw-source="[Interface](microsoft-windows-netbt-interfaces-interface.md)">Interface</a> setting. <em>Identifier</em> is a string with a maximum length of 256 characters.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Parent Hierarchy


[microsoft-windows-netbt-](microsoft-windows-netbt.md) | [Interfaces](microsoft-windows-netbt-interfaces.md) | [Interface](microsoft-windows-netbt-interfaces-interface.md) | **Identifier**

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


[Interface](microsoft-windows-netbt-interfaces-interface.md)

 

 







