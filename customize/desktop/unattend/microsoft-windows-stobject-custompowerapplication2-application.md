---
title: Application
description: Application
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 53198375-d0bb-426e-a716-f9e867729fa8
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Application


`Application` specifies the full path to the application specified by [CustomPowerApplication2](microsoft-windows-stobject-custompowerapplication2.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path</em></p></td>
<td><p>Specifies the full path and the executable file name for <a href="microsoft-windows-stobject-custompowerapplication2.md" data-raw-source="[CustomPowerApplication2](microsoft-windows-stobject-custompowerapplication2.md)">CustomPowerApplication2</a>. For example,</p>
<pre class="syntax" space="preserve"><code>%ProgramFiles%\CustomPower\Application.exe</code></pre>
<p><em>Path</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication2](microsoft-windows-stobject-custompowerapplication2.md) | **Application**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows `CustomPowerApplication2` Application.exe with `parameter -param`. `IconID` and `ItemName` are included in Resource.dll.

```
<CustomPowerApplication2>
   <Application>%ProgramFiles%\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication2>
```

## Related topics


[CustomPowerApplication2](microsoft-windows-stobject-custompowerapplication2.md)

 

 







