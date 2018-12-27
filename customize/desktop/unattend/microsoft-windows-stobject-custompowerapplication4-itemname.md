---
title: ItemName
description: ItemName
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 30dd654a-3f59-468e-9390-acd66da7794d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ItemName


`ItemName` is the display name of [CustomPowerApplication4](microsoft-windows-stobject-custompowerapplication4.md).

To use a different `ItemName` for each language, create a resource file, and refer to it using the format: "filename.dll,-referenceid". For information on creating localized text versions for this setting, see the topic [Using the MUI with Applications](http://go.microsoft.com/fwlink/?LinkId=140252).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Name</em></p></td>
<td><p>Specifies the display name to use <a href="microsoft-windows-stobject-custompowerapplication4.md" data-raw-source="[CustomPowerApplication4](microsoft-windows-stobject-custompowerapplication4.md)">CustomPowerApplication4</a>.</p>
<p><code>ItemName</code> is represented as @<em>dllname,-resourceid</em>, where <em>dllname</em> is the full path to the resource DLL, including environment variables. For example,</p>
<pre class="syntax" space="preserve"><code>@%ProgramFiles%\Microsoft Shared\Resource.dll,-100</code></pre>
<p><em>Name</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication4](microsoft-windows-stobject-custompowerapplication4.md) | **ItemName**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows `CustomPowerApplication4` Application.exe with `parameter -param`. `IconID` and `ItemName` included in the Resource.dll file.

```
<CustomPowerApplication4>
   <Application>C:\Program Files\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication4>
```

## Related topics


[CustomPowerApplication4](microsoft-windows-stobject-custompowerapplication4.md)

 

 







