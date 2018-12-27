---
title: Application
description: Application
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 24420a39-35e1-4dc6-97ef-eaf12e3128a2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Application


`Application` specifies the full path to the application specified by [CustomPowerApplication4](microsoft-windows-stobject-custompowerapplication4.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path</em></p></td>
<td><p>Specifies the full path and the executable file name for <a href="microsoft-windows-stobject-custompowerapplication4.md" data-raw-source="[CustomPowerApplication4](microsoft-windows-stobject-custompowerapplication4.md)">CustomPowerApplication4</a>. For example,</p>
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


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication4](microsoft-windows-stobject-custompowerapplication4.md) | **Application**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows `CustomPowerApplication4` Application.exe with `parameter -param`. `IconID` and `ItemName` are included in Resource.dll.

```
<CustomPowerApplication4>
   <Application>%ProgramFiles%\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication4>
```

## Related topics


[CustomPowerApplication4](microsoft-windows-stobject-custompowerapplication4.md)

 

 







