---
title: CommandLabelDisplay
description: CommandLabelDisplay
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8e58e8cb-f74b-4086-bf59-12d142187c62
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# CommandLabelDisplay


`CommandLabelDisplay` specifies whether tooltips appear next to the icons in the Internet Explorer Command Bar.

The Command Bar appears at the top of the Internet Explorer screen, and includes items such as **Home**, **Print**, **Page**, and **Tools**.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>0</p></td>
<td><p>Shows a tooltip next to selected icons in the Command Bar.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>Shows a tooltip next to each icon in the Command Bar.</p></td>
</tr>
<tr class="odd">
<td><p>2</p></td>
<td><p>Shows only icons in the Command Bar.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **CommandLabelDisplay**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to configure the Command Bar to show a tooltip next to each icon in the Command Bar.

```
<CommandLabelDisplay>1</CommandLabelDisplay>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







