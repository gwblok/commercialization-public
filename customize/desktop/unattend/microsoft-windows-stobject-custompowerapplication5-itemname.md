---
title: ItemName
description: ItemName
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7f584e06-7dca-44f4-9585-cf2fdc150ec2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ItemName


`ItemName` is the display name of [CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md).

To use a different `ItemName` for each language, create a resource file, and refer to it using the format: “filename.dll,-referenceid”. For information on creating localized text versions for this setting, see the topic [Using the MUI with Applications](http://go.microsoft.com/fwlink/?LinkId=140252).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Name</em></p></td>
<td><p>Specifies the display name to use for <a href="microsoft-windows-stobject-custompowerapplication5.md" data-raw-source="[CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md)">CustomPowerApplication5</a>.</p>
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


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md) | **ItemName**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

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

 

 







