---
title: LockToolbars
description: LockToolbars
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 89e1f5ce-3ccb-4b89-a001-00aafa490a38
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# LockToolbars


`LockToolbars` specifies whether the toolbars in Internet Explorer are locked in position.

By default, menu toolbars are not visible and must be enabled. Selected toolbars can be moved by clicking and dragging the separator bars on the left side of the toolbar.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>true</code></p></td>
<td><p>Menus are locked in position.</p></td>
</tr>
<tr class="even">
<td><p><code>false</code></p></td>
<td><p>Selected toolbars can be moved by clicking and dragging the separator bars on the left side of the toolbar.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **LockToolbars**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to lock the Internet Explorer toolbars.

```
<LockToolbars>true</LockToolbars> 
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







