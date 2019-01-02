---
title: DBPath
description: DBPath
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0f65ba6b-c002-4119-bef4-cc69e748b3d6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DBPath


`DBPath` specifies the path to the license database.

## Value


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Database_path</em></p></td>
<td><p>Specifies the path to the license database. <em>Database_path</em> is a string. The default setting is <code>%SystemRoot%\System32\LSystem</code>.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-TerminalServices-LicenseServer](microsoft-windows-terminalservices-licenseserver.md) | **DBPath**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TerminalServices-LicenseServer](microsoft-windows-terminalservices-licenseserver.md).

## XML Example


The following XML output specifies the path to the license database.

```
<DBPath>%SystemRoot%\System32\LSystem</DBPath>
```

## Related topics


[Microsoft-Windows-TerminalServices-LicenseServer](microsoft-windows-terminalservices-licenseserver.md)

 

 







