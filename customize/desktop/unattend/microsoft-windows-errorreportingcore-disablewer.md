---
title: DisableWER
description: DisableWER
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: da658e7e-c647-45a0-9500-0092c4fc7f1d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisableWER


`DisableWER` disables Windows Error Reporting. You may want to disable error-reporting functionality when you are deploying Windows in large, managed environments.

For more information on privacy concerns about error reporting, see [this Microsoft website](http://go.microsoft.com/fwlink/?linkid=50163).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>0</strong></p></td>
<td><p>Enables Windows Error Reporting</p></td>
</tr>
<tr class="even">
<td><p><strong>1</strong></p></td>
<td><p>Disables Windows Error Reporting</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-ErrorReportingCore](microsoft-windows-errorreportingcore.md) | **DisableWER**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures this component supports, see [Microsoft-Windows-ErrorReportingCore](microsoft-windows-errorreportingcore.md).

## XML Example


The following XML output disables Windows Error Reporting.

```
<DisableWER>1</DisableWER>
```

## Related topics


[Microsoft-Windows-ErrorReportingCore](microsoft-windows-errorreportingcore.md)

 

 







