---
title: OptIn
description: OptIn
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 506fbe6c-21c8-4177-9719-3215a74753d6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# OptIn


`OptIn` specifies whether installation statistics are sent to Microsoft.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that installation statistics are sent to Microsoft.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that installation statistics are not sent to Microsoft. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [Diagnostics](microsoft-windows-setup-diagnostics.md) | **OptIn**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to change this setting so that no information is sent.

```
<Diagnostics>
   <OptIn>false</OptIn>
</Diagnostics>
```

## Related topics


[Diagnostics](microsoft-windows-setup-diagnostics.md)

 

 







