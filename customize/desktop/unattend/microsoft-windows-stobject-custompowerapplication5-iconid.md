---
title: IconID
description: IconID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 008f04cf-6a90-41b5-bf6f-e816e82e6deb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# IconID


`IconID` specifies the full path to the resource DLL that contains the icon to use with [CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md).

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
<td><p>Specifies the resource ID of the icon to use for <a href="microsoft-windows-stobject-custompowerapplication5.md" data-raw-source="[CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md)">CustomPowerApplication5</a>.</p>
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


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication5](microsoft-windows-stobject-custompowerapplication5.md) | **IconID**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows `CustomPowerApplication5` Application.exe with `parameter -param`. `IconID` and `ItemName` are included in the Resource.dll file.

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

 

 







