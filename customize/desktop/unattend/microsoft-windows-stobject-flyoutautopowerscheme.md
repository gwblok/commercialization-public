---
title: FlyoutAutoPowerScheme
description: FlyoutAutoPowerScheme
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 55161779-c594-43dc-a0d5-17f9c0942d7d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# FlyoutAutoPowerScheme


`FlyoutAutoPowerScheme` is the globally unique identifier (GUID) of the Battery Meter Fly-out Balanced power plan.

You can use the Powercfg command-line tool to list the available power plans. For example,

```
powercfg -LIST

## Existing Power Schemes (* Active)

Power Scheme GUID: 381b4222-f694-41f0-9685-ff5bb260df2e  (Balanced) *
Power Scheme GUID: 8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c  (High performance)
Power Scheme GUID: a1841308-3541-4fab-bc81-f71556f20b4a  (Power saver)
```

For more information, see the Powercfg command-line Help.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>GUID</em></p></td>
<td><p>Specifies the GUID of the power plan to display in the Battery Meter Fly-out for the Balanced power scheme configuration.</p>
<p><em>GUID</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | **FlyoutAutoPowerScheme**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows how to configure `FlyoutAutoPowerScheme`.

```
<FlyoutAutoPowerScheme>391b4222-f694-41f0-9685-ff5bb260df2e</FlyoutAutoPowerScheme>
```

## Related topics


[Microsoft-Windows-stobject](microsoft-windows-stobject.md)

 

 







