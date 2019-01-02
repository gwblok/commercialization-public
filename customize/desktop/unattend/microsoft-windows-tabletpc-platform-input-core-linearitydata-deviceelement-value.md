---
title: Value
description: Value
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5c57d165-dfa6-4a5f-af29-432188dc15cf
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Value


`Value` specifies the value of the [DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md).

**Note**  
This element does not appear in the **Properties** pane of Windows System Image Manager (Windows SIM) until you add [DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md) to the answer file.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Value</em></p></td>
<td><p>Specifies the value of the <a href="microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md" data-raw-source="[DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md)">DeviceElement</a>. <em>Value</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md)| [LinearityData](microsoft-windows-tabletpc-platform-input-core-linearitydata.md)| [DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md) | **Value**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md).

## XML Example


The following XML output shows how to configure `Value`.

```
<LinearityData>
   <DeviceElement wcm:action="add" wcm:keyValue="MyKey">11</DeviceElement>
</LinearityData>
```

## Related topics


[DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md)

 

 







