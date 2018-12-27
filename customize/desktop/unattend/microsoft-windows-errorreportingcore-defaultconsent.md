---
title: DefaultConsent
description: DefaultConsent
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 767801d1-ca20-40ab-9129-d1436ac305eb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DefaultConsent


`DefaultConsent` specifies in what circumstances the user is asked whether to send an error report. For more information about error reporting privacy concerns, see [this Microsoft website](http://go.microsoft.com/fwlink/?linkid=50163).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>0</strong> or <strong>1</strong></p></td>
<td><p>Always ask the user whether to send an error report. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>2</strong></p></td>
<td><p>Ask the user for everything except for basic parameters such as application name, version, and module name that are sent automatically.</p></td>
</tr>
<tr class="odd">
<td><p><strong>3</strong></p></td>
<td><p>Ask the user for everything except for basic parameters that are likely to be safe, such as application name, version, and module name, and data. Send these items automatically.</p></td>
</tr>
<tr class="even">
<td><p><strong>4</strong></p></td>
<td><p>Do not ask the user; send all error reports automatically.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-ErrorReportingCore](microsoft-windows-errorreportingcore.md) | **DefaultConsent**

## Valid Configuration Passes


specialize

## Applies To


For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-ErrorReportingCore](microsoft-windows-errorreportingcore.md).

## XML Example


The following XML output specifies that all data is sent automatically.

```
<DefaultConsent>4</DefaultConsent>
```

## Related topics


[Microsoft-Windows-ErrorReportingCore](microsoft-windows-errorreportingcore.md)

 

 







