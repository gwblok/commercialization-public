---
title: Application
description: Application
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b548f704-a5a7-4c8f-9f09-cfb261dc7423
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Application


`Application `specifies the full path to the application specified by [CustomPowerApplication6](microsoft-windows-stobject-custompowerapplication6.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path</em></p></td>
<td><p>Specifies the full path and the executable file name for <a href="microsoft-windows-stobject-custompowerapplication6.md" data-raw-source="[CustomPowerApplication6](microsoft-windows-stobject-custompowerapplication6.md)">CustomPowerApplication6</a>. For example,</p>
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


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication6](microsoft-windows-stobject-custompowerapplication6.md) | **Application**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows `CustomPowerApplication6` Application.exe with `parameter -param`. `IconID` and `ItemName` are included in Resource.dll.

```
<CustomPowerApplication6>
   <Application>%ProgramFiles%\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication6>
```

## Related topics


[CustomPowerApplication6](microsoft-windows-stobject-custompowerapplication6.md)

 

 







