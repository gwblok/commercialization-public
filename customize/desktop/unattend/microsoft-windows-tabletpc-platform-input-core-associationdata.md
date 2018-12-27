---
title: AssociationData
description: AssociationData
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a5562e59-ea3d-4b17-a537-1e11b427b1f5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# AssociationData

`AssociationData` contains one or more instances of [AssociationElement](microsoft-windows-tabletpc-platform-input-core-associationdata-associationelement.md). The AssociationElement specifies information to associate a Tablet PC monitor to the digitizer. Add a separate AssociationElement for each Tablet PC monitor that you want to associate to a digitizer.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AssociationElement](microsoft-windows-tabletpc-platform-input-core-associationdata-associationelement.md) | Specifies information to associate a Tablet PC monitor to a digitizer. |

## Parent Hierarchy

[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md) | **AssociationData**

## Valid Configuration Passes

offlineServicing

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md).

## XML Example

The following XML output shows how to configure `AssociationData` to associate two Tablet PC monitors to two digitizers on the same system, using the key values: Monitor1, Monitor2, and Monitor3.

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
