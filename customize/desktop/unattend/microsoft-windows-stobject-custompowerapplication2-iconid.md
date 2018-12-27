---
title: IconID
description: IconID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a80a092c-eb04-4279-bb18-f3bbef7702f2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# IconID


`IconID` specifies the full path to the resource DLL that contains the icon to use with [CustomPowerApplication2](microsoft-windows-stobject-custompowerapplication2.md).

This setting is optional.

To use a different IconID for each language, create a resource file, and refer to it using the format: "filename.dll,-referenceid". For information on creating localized text versions for this setting, see the topic [Using the MUI with Applications](http://go.microsoft.com/fwlink/?LinkId=140252).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>ID</em></p></td>
<td><p>Specifies the resource ID of the icon to use for <a href="microsoft-windows-stobject-custompowerapplication2.md" data-raw-source="[CustomPowerApplication2](microsoft-windows-stobject-custompowerapplication2.md)">CustomPowerApplication2</a>.</p>
<p><code>IconID</code> is represented as @<em>dllname,-resourceID</em>, where <em>dllname</em> must include a full path to the resource DLL. For example,</p>
<pre class="syntax" space="preserve"><code>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</code></pre>
<p><em>ID</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication2](microsoft-windows-stobject-custompowerapplication2.md) | **IconID**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows `CustomPowerApplication2` Application.exe with `parameter -param`. `IconID` and `ItemName` are included in the Resource.dll file.

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

 

 







