---
title: Parameters
description: Parameters
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4590bd0c-d23c-489a-9dd4-bb8e87947017
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Parameters


`Parameters` specifies the arguments to add to [CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md).

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
<td><p>Specifies the arguments to use when running the application specified by <a href="microsoft-windows-stobject-custompowerapplication5.md" data-raw-source="[CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md)">CustomPowerApplication5</a>.</p>
<p><em>Parameters</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md) | **Parameters**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows `CustomPowerApplication5` Application.exe with `parameter -param`. `IconID` and `ItemName` are included in Resource.dll.

```
<CustomPowerApplication5>
   <Application>C:\Program Files\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication5>
```

## Related topics


[CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md)

 

 







