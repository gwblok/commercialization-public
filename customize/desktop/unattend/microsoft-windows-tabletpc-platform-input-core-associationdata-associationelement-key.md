---
title: Key
description: Key
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 66564dca-44bc-4933-9518-d513b05ee3f6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Key


`Key` specifies a unique key for the [AssociationElement](microsoft-windows-tabletpc-platform-input-core-associationdata-associationelement.md).

**Note**  
-   This element does not appear in the **Properties** pane of Windows System Image Manager (Windows SIM) until you add [AssociationElement](microsoft-windows-tabletpc-platform-input-core-associationdata-associationelement.md) to the answer file.

-   The value for `Key` is added to the answer file as an attribute of the [AssociationElement](microsoft-windows-tabletpc-platform-input-core-associationdata-associationelement.md) element. The attribute `wcm:keyValue` is used to identify each unique association. For example, you can specify three different associations by using the `Key` values of **Monitor1**, **Monitor2**, and **Monitor3**.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Key</em></p></td>
<td><p>Specifies a unique key for the <a href="microsoft-windows-tabletpc-platform-input-core-associationdata-associationelement.md" data-raw-source="[AssociationElement](microsoft-windows-tabletpc-platform-input-core-associationdata-associationelement.md)">AssociationElement</a>. <em>Key</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md)| [AssociationData](microsoft-windows-tabletpc-platform-input-core-associationdata.md)| [AssociationElement](microsoft-windows-tabletpc-platform-input-core-associationdata-associationelement.md) | **Key**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md).

## XML Example


The following XML output shows how to configure `AssociationElement` to associate two Tablet PC monitors to three digitizers on the same system, using the key values: Monitor1, Monitor2, and Monitor3.

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

 

 







