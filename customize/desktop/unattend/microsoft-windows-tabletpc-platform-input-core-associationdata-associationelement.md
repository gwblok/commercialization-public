---
title: AssociationElement
description: AssociationElement
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0c919980-49bd-466d-a99e-cf27ae5e3053
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# AssociationElement

`AssociationElement` specifies information to associate a Tablet PC monitor to the digitizer.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Key](microsoft-windows-tabletpc-platform-input-core-associationdata-associationelement-key.md) | Specifies a unique key for the <code>AssociationElement</code>. |
| [Value](microsoft-windows-tabletpc-platform-input-core-associationdata-associationelement-value.md) | Specifies information to associate a Tablet PC monitor to a digitizer. |

## Parent Hierarchy

[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md) | [AssociationData](microsoft-windows-tabletpc-platform-input-core-associationdata.md) | **AssociationElement**

## Valid Configuration Passes

offlineServicing

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md).

## XML Example

The following XML output shows how to configure `AssociationElement`.

> [!Note]
> In Windows System Image Manager, you can enter values with quotation marks. In the XML, the quotation marks are replaced with `&quot;`.

```XML
<AssociationData>
   <AssociationElement wcm:action="add" wcm:keyValue="Monitor1">&quot;hid#VID_1B96&amp;PID_0008&amp;REV_2100&amp;mi_01&amp;col01&quot;=&quot;PCI\\VEN_8086&amp;DEV_4102&amp;SUBSYS_16B510CF|FUJ5812&quot;</AssociationElement>
   <AssociationElement wcm:action="add" wcm:keyValue="Monitor2">&quot;hid#VID_1B96&amp;PID_0008&amp;REV_2100&amp;mi_01&amp;col02&quot;=&quot;PCI\\VEN_8086&amp;DEV_4102&amp;SUBSYS_16B510CF|FUJ5812&quot;</AssociationElement>
</AssociationData>
   <AssociationElement wcm:action="add" wcm:keyValue="Monitor3">&quot;hid#VID_1B96&amp;PID_0008&amp;REV_2100&amp;mi_01&amp;col03&quot;=&quot;PCI\\VEN_8086&amp;DEV_4102&amp;SUBSYS_16B510CF|FUJ5812&quot;</AssociationElement>
</AssociationData>
```

## Related topics

[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md)
