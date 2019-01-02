---
title: ShowLeftAddressToolbar
description: ShowLeftAddressToolbar
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3eaac318-3d3a-4750-800a-99a5f239bad5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ShowLeftAddressToolbar


`ShowLeftAddressToolbar` specifies where on the **Address** bar the **Stop** and **Refresh** buttons appear in Windows Internet Explorer.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>true</p></td>
<td><p>Shows the <strong>Stop</strong> and <strong>Refresh</strong> buttons on the left side of the <strong>Address</strong> bar.</p></td>
</tr>
<tr class="even">
<td><p>false</p></td>
<td><p>Shows the <strong>Stop</strong> and <strong>Refresh</strong> buttons on the right side of the <strong>Address</strong> bar.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **ShowLeftAddressToolbar**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output specifies that the **Stop** and **Refresh** buttons show on the left side of the **Address** bar in Internet Explorer.

```
<ShowLeftAddressToolbar>true</ShowLeftAddressToolbar>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







