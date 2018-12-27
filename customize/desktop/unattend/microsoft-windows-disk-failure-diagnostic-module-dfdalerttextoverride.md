---
title: DfdAlertTextOverride
description: DfdAlertTextOverride
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 552e4902-e69d-4d89-9464-b0e3f422dac2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DfdAlertTextOverride


`DfdAlertTextOverride` specifies a customized error message to display when the Windows Disk Diagnostic warning dialog box appears. You can use this customized text to specify support information, a website location, or other information.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Custom_Message</em></p></td>
<td><p>Specifies a customized message to display in the Windows Disk Diagnostic warning dialog box.</p>
<p><em>Custom_Message</em> is a string with a maximum of 512 characters.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


offlineServicing

generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-Disk-Failure-Diagnostic-Module](microsoft-windows-disk-failure-diagnostic-module.md) | **DfdAlertTextOverride**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Disk-Failure-Diagnostic-Module](microsoft-windows-disk-failure-diagnostic-module.md).

## XML Example


The following XML output shows how to configure Windows Disk Diagnostic.

```
<EnabledScenarioExecutionLevel>2</EnabledScenarioExecutionLevel>
<DfdAlertTextOverride>Custom alert text that describes additional support information</DfdAlertTextOverride>
```

## Related topics


[Microsoft-Windows-Disk-Failure-Diagnostic-Module](microsoft-windows-disk-failure-diagnostic-module.md)

 

 







