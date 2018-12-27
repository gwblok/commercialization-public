---
title: fDisabledAllowList
description: fDisabledAllowList
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a150bf8c-8de2-4703-9433-ab153344966f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# fDisabledAllowList


`fDisabledAllowList` specifies whether the Allow list is checked and enforced.

## Value


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>0</strong></p></td>
<td><p>Specifies that the Allow list is checked and enforced. This is the default setting.</p></td>
</tr>
<tr class="even">
<td><p><strong>1</strong></p></td>
<td><p>Specifies that the Allow list is not checked and enforced.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


offlineServicing

generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-TerminalServices-Publishing-WMIProvider](microsoft-windows-terminalservices-publishing-wmiprovider.md) | **fDisabledAllowList**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TerminalServices-Publishing-WMIProvider](microsoft-windows-terminalservices-publishing-wmiprovider.md).

## XML Example


The following XML output specifies that the Allow list is not checked and enforced.

```
<fDisabledAllowList>1</fDisabledAllowList>
```

## Related topics


[Microsoft-Windows-TerminalServices-Publishing-WMIProvider](microsoft-windows-terminalservices-publishing-wmiprovider.md)

 

 







