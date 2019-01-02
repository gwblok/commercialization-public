---
title: Key
description: Key
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4c5ef510-a31d-489a-a7e8-d279b8be77b6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Key


`Key` specifies a unique key for the [DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md).

**Note**  
-   This element does not appear in the **Properties** pane of Windows System Image Manager (Windows SIM) until you add [DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md) to the answer file.

-   The value for `Key` is added to the answer file as an attribute of [DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md). The attribute `wcm:keyValue` is used to identify each unique device. For example, you can specify three different IP addresses by using the `Key` values of **MyKey1**, **MyKey2**, and **MyKey3**.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Key</em></p></td>
<td><p>Specifies a unique key for the <a href="microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md" data-raw-source="[DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md)">DeviceElement</a>. <em>Key</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md)| [LinearityData](microsoft-windows-tabletpc-platform-input-core-linearitydata.md)| [DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md) | **Key**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md).

## XML Example


The following XML output shows how to configure `Key`.

```
<NameServerList>
   <IpAddress wcm:action="add" wcm:keyValue="MyKey">MyValue</IpAddress> 
   </NameServerList>
```

## Related topics


[DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md)

 

 







