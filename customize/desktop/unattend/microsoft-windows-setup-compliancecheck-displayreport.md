---
title: DisplayReport
description: DisplayReport
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d01d4ae2-1d9a-46ab-a72e-aa2360da90c6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisplayReport


`DisplayReport` specifies in what circumstances the user interface (UI) is displayed for this item.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>OnError</strong></p></td>
<td><p>Specifies that the UI is displayed on error. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>Never</strong></p></td>
<td><p>Specifies that the UI is never displayed, even for serious errors. An error is logged, and installation terminates.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [ComplianceCheck](microsoft-windows-setup-compliancecheck.md) | **DisplayReport**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output specifies that the installation is to run in guaranteed quiet mode without displaying to the UI.

```
<ComplianceCheck>
   <DisplayReport>Never</DisplayReport>
</ComplianceCheck>
```

## Related topics


[ComplianceCheck](microsoft-windows-setup-compliancecheck.md)

 

 







