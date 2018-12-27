---
title: UseConfigurationSet
description: UseConfigurationSet
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 680ae979-d918-4112-b277-7e5233a0266a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# UseConfigurationSet


`UseConfigurationSet` specifies whether to use a configuration set for Windows Setup.

A configuration set is a folder that contains additional device drivers, applications, or other binaries that you want to add to Windows during installation. You can create a configuration set in Windows System Image Manager (Windows SIM). Configuration sets are useful when a network share is not available. Configuration sets can be stored on removable media and used to install Windows in the field. Creating a configuration set in Windows SIM exports binaries referenced in the unattended installation answer file and puts them together into a self-contained file set. Windows SIM automatically appends the paths to the configuration set when it validates and saves the answer file.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that a configuration set is used.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that a configuration set is not used. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | **UseConfigurationSet**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output specifies that a configuration set is used.

```
<UseConfigurationSet>true</UseConfigurationSet>
```

## Related topics


[microsoft-windows-setup-](microsoft-windows-setup.md)

 

 







