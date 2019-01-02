---
title: ConfigurationFlags
description: ConfigurationFlags
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7ed5282a-1efa-43f8-91a9-97635cec0e0b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ConfigurationFlags


`ConfigurationFlags` specifies whether Remote Access Service (RAS) is configured.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that RAS is configured.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that RAS is not configured. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-RasServer](microsoft-windows-rasserver.md) | **ConfigurationFlags**

## Valid Configuration Passes


specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-RasServer](microsoft-windows-rasserver.md).

## XML Example


The following XML output enables RAS and sets the Router type to enable Local Area Network (LAN) access.

```
<ConfigurationFlags>true</ConfigurationFlags>
<RouterType>2</RouterType>
```

## Related topics


[Microsoft-Windows-RasServer](microsoft-windows-rasserver.md)

 

 







