---
title: Application
description: Application
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0d348f52-96ce-41fb-9506-cc12b44e8d20
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Application


`Application` specifies the full path to the application specified by [CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path</em></p></td>
<td><p>Specifies the full path and the executable file name for <a href="microsoft-windows-stobject-custompowerapplication5.md" data-raw-source="[CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md)">CustomPowerApplication5</a>. For example,</p>
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


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md) | **Application**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows `CustomPowerApplication5` Application.exe with `parameter -param`. `IconID` and `ItemName` are included in Resource.dll.

```
<CustomPowerApplication5>
   <Application>%ProgramFiles%\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication5>
```

## Related topics


[CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md)

 

 







