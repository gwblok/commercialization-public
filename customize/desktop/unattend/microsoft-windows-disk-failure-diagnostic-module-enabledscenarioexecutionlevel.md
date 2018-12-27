---
title: EnabledScenarioExecutionLevel
description: EnabledScenarioExecutionLevel
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 505a4ce3-834c-429e-9747-0cadeed5047c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# EnabledScenarioExecutionLevel


`EnabledScenarioExecutionLevel` enables the Windows Disk Diagnostic feature.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>1</strong></p></td>
<td><p>Disables Windows Disk Diagnostic.</p></td>
</tr>
<tr class="even">
<td><p><strong>2</strong></p></td>
<td><p>Enables Windows Disk Diagnostic.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


offlineServicing

generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-Disk-Failure-Diagnostic-Module](microsoft-windows-disk-failure-diagnostic-module.md) | **EnabledScenarioExecutionLevel**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Disk-Failure-Diagnostic-Module](microsoft-windows-disk-failure-diagnostic-module.md).

## XML Example


The following XML output shows how to configure Windows Disk Diagnostic.

```
<EnabledScenarioExecutionLevel>2</EnabledScenarioExecutionLevel>
<DfdAlertTextOverride>Custom alert text that describes additional support information</DfdAlertTextOverride>
```

## Related topics


[Microsoft-Windows-Disk-Failure-Diagnostic-Module](microsoft-windows-disk-failure-diagnostic-module.md)

 

 







