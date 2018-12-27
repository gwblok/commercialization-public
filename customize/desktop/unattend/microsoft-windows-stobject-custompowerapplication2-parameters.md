---
title: Parameters
description: Parameters
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0f1c2035-0f78-4bcf-9431-32a75edd5285
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Parameters


`Parameters` specifies the arguments to add to [CustomPowerApplication2](microsoft-windows-stobject-custompowerapplication2.md).

This setting is optional.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Parameters</em></p></td>
<td><p>Specifies the arguments to use when running the application specified by <a href="microsoft-windows-stobject-custompowerapplication2.md" data-raw-source="[CustomPowerApplication2](microsoft-windows-stobject-custompowerapplication2.md)">CustomPowerApplication2</a>.</p>
<p><em>Parameters</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication2](microsoft-windows-stobject-custompowerapplication2.md) | **Parameters**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows `CustomPowerApplication2` Application.exe with `parameter -param`. `IconID` and `ItemName` are included in Resource.dll.

```
<CustomPowerApplication2>
   <Application>C:\Program Files\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication2>
```

## Related topics


[CustomPowerApplication2](microsoft-windows-stobject-custompowerapplication2.md)

 

 







