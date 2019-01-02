---
title: Value
description: Value
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 53b88df2-5e96-4335-80b9-81a9ffec95c5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Value


`Value` specifies information to associate a Tablet PC monitor to a digitizer.

This setting requires the string values of: *DigitizerPattern*, *AdapterPattern*, and *MonitorPattern*. For information about finding the Device String or Device ID values, see the MSDN articles: [DISPLAY\_DEVICE](http://go.microsoft.com/fwlink/?LinkId=140784) and [EnumDisplayDevices](http://go.microsoft.com/fwlink/?LinkId=140787).

**Note**  
Some portions of these patterns may change depending on installation order. For best results, only use portions of the string that are unique to the device.

 

An association is made between the digitizer and monitor if:

The *DigitizerPattern* matches exactly one digitizer.

The combination of *AdapterPattern* and *MonitorPattern* match exactly one monitor.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>&quot;<em>DigitizerPattern</em>&quot;=&quot;<em>AdapterPattern</em>|<em>MonitorPattern</em>&quot;</p></td>
<td><p>Specifies the information to associate the Tablet PC monitor to the digitizer.</p>
<p><em>DigitizerPattern</em> is a substring that matches the Device Instance Path of the digitizer.</p>
<p><em>AdapterPattern</em> is a substring that matches a unique pattern from either the DeviceString or DeviceID fields from DISPLAY_DEVICE.</p>
<p><em>MonitorPattern</em> is a substring that matches a unique pattern from either the DeviceString or DeviceID fields from DISPLAY_DEVICE.</p>
<p>It is not required to match these string values completely. You can provide just the portions of the string that are unique to the device.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md)| [AssociationData](microsoft-windows-tabletpc-platform-input-core-associationdata.md)| [AssociationElement](microsoft-windows-tabletpc-platform-input-core-associationdata-associationelement.md) | **Value**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md).

## XML Example


The following XML output shows how to configure the `AssociationData` setting to associate a Tablet PC monitor to three digitizers on the same system.

For the Tablet PC monitor in this example, the DeviceString is "MONITOR\\FAB1234B\\{12ab34cd56-ef76-ab54-3210fe}", and the DeviceID field is "Generic PnP Monitor". The substring FAB1234B is chosen for *Monitor\_pattern* in the example, though other choices of unique substrings are also possible.

**Note**  
In Windows System Image Manager, you can enter values with quotation marks. In the XML, the quotation marks are replaced with `&quot;`.

 

```
<AssociationData>
   <AssociationElement wcm:action="add" wcm:keyValue="Monitor1">&quot;hid#VID_1B96&amp;PID_0008&amp;REV_2100&amp;mi_01&amp;col01&quot;=&quot;PCI\\VEN_8086&amp;DEV_4102&amp;SUBSYS_16B510CF|FUJ5812&quot;</AssociationElement>
   <AssociationElement wcm:action="add" wcm:keyValue="Monitor2">&quot;hid#VID_1B96&amp;PID_0008&amp;REV_2100&amp;mi_01&amp;col02&quot;=&quot;PCI\\VEN_8086&amp;DEV_4102&amp;SUBSYS_16B510CF|FUJ5812&quot;</AssociationElement>
</AssociationData>
   <AssociationElement wcm:action="add" wcm:keyValue="Monitor3">&quot;hid#VID_1B96&amp;PID_0008&amp;REV_2100&amp;mi_01&amp;col03&quot;=&quot;PCI\\VEN_8086&amp;DEV_4102&amp;SUBSYS_16B510CF|FUJ5812&quot;</AssociationElement>
</AssociationData>
```

## Related topics


[AssociationElement](microsoft-windows-tabletpc-platform-input-core-associationdata-associationelement.md)

 

 







