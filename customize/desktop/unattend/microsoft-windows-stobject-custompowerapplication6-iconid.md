---
title: IconID
description: IconID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 52c3b012-37c5-47b3-8cee-4901b8be997e
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# IconID


`IconID` specifies the full path to the resource DLL that contains the icon to use with [CustomPowerApplication6](microsoft-windows-stobject-custompowerapplication6.md).

This setting is optional.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>ID</em></p></td>
<td><p>Specifies the resource ID of the icon to use for <a href="microsoft-windows-stobject-custompowerapplication6.md" data-raw-source="[CustomPowerApplication6](microsoft-windows-stobject-custompowerapplication6.md)">CustomPowerApplication6</a>.</p>
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


[Microsoft-Windows-stobject](microsoft-windows-stobject.md) | [CustomPowerApplication6](microsoft-windows-stobject-custompowerapplication6.md) | **IconID**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-stobject](microsoft-windows-stobject.md).

## XML Example


The following XML output shows `CustomPowerApplication6` Application.exe with `parameter -param`. `IconID` and `ItemName` are included in the Resource.dll file.

```
<CustomPowerApplication6>
   <Application>C:\Program Files\CustomPower\Application.exe</Application>
   <IconID>@%ProgramFiles%\Microsoft Shared\Resource.dll,-200</IconID>
   <ItemName>%ProgramFiles%\Microsoft Shared\Resource.dll,-100</ItemName>
   <Parameters>-param</Parameters>
</CustomPowerApplication6>
```

## Related topics


[CustomPowerApplication6](microsoft-windows-stobject-custompowerapplication6.md)

 

 







