---
title: UILanguage
description: UILanguage
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 37505afa-e9e9-4c0a-9dc7-d0e4f90e2bb8
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# UILanguage


`UILanguage` specifies the language that is used to display menu items in Windows Setup and Windows Deployment Services.

In addition to this `UILanguage` setting, a [UILanguage](microsoft-windows-international-core-winpe-uilanguage.md) setting is used to specify the default user interface (UI) language of the Windows installation.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>UI_language</em></p></td>
<td><p>Indicates the language of the user interface to use during Windows Setup or Windows Deployment Services.</p>
<p>The <em>UI_language</em> string is based on the language-tagging conventions of RFC 3066. The pattern <em>language</em>-<em>region</em> is used, where <em>language</em> is a language code and <em>region</em> is a country or region identifier (for example, <strong>en-US</strong>, <strong>fr-FR</strong>, or <strong>es-ES</strong>).</p>
<p>This value is not case-sensitive.</p>
<p>For a list of supported languages, locales, and identifiers, see <a href="http://go.microsoft.com/fwlink/p/?linkid=200318" data-raw-source="[Available Language Packs](http://go.microsoft.com/fwlink/p/?linkid=200318)">Available Language Packs</a>.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Parent Hierarchy


[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md) | [SetupUILanguage](microsoft-windows-international-core-winpe-setupuilanguage.md) | **UILanguage**

## Valid Configuration Passes


windowsPE

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md).

## XML Example


The following example shows how to configure the Windows Setup UI language to display French (France).

```
   <SetupUILanguage>
       <UILanguage>fr-FR</UILanguage>
   </SetupUILanguage>
```

## Related topics


[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md)

[Microsoft-Windows-International-Core](microsoft-windows-international-core.md)

 

 







