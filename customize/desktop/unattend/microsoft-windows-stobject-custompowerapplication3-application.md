---
title: Application
description: Application
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 50125f40-9c37-4eb4-a8f5-aac7ad0ac922
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Application


`Application` specifies the full path to the application specified by [CustomPowerApplication3](microsoft-windows-stobject-custompowerapplication3.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path</em></p></td>
<td><p>Specifies the full path and the executable file name for <a href="microsoft-windows-stobject-custompowerapplication3.md" data-raw-source="[CustomPowerApplication3](microsoft-windows-stobject-custompowerapplication3.md)">CustomPowerApplication3</a>. For example,</p>
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


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication3](microsoft-windows-stobject-custompowerapplication3.md) | **Application**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows `CustomPowerApplication3` Application.exe with `parameter -param`. `IconID` and `ItemName` are included in Resource.dll.

```
<CustomPowerApplication3>
   <Application>%ProgramFiles%\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication3>
```

## Related topics


[CustomPowerApplication3](microsoft-windows-stobject-custompowerapplication3.md)

 

 







