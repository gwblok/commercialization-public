---
title: UILanguage
description: UILanguage
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 23da0462-281c-4f2b-a55d-3a395c86b433
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# UILanguage


`UILanguage` specifies the language that will be used as the default system language to display user interface (UI) items (such as menus, dialog boxes, and Help files).

This setting is used by Windows Setup and Windows Deployment Services.

For a list of supported languages, see [Supported Language Packs and Default Settings](http://go.microsoft.com/fwlink/p/?linkid=200317).

In upgrade installation types, this setting is ignored. In upgrade installations, you can upgrade only from the same language.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>UI_language</em></p></td>
<td><p>Specifies the language of the UI.</p>
<p>The <em>UI_language</em> string is based on the language-tagging conventions of RFC 3066. The pattern <em>language-region</em> is used, where <em>language</em> is a language code and <em>region</em> is a country or region identifier (for example, <strong>en-US</strong>, <strong>fr-FR</strong>, or <strong>es-ES</strong>).</p>
<p>This value is not case-sensitive.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Parent Hierarchy


[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md) | **UILanguage**

## Valid Configuration Passes


windowsPE

## Applies To


For the list of the Windows editions and architectures that this component supports, see [microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md).

## XML Example


The following example shows how to set the UI language to German (Germany).

```
<InputLocale>0407:00000407</InputLocale> 
<SystemLocale>de-DE</SystemLocale> 
<UILanguage>de-DE</UILanguage> 
<UserLocale>de-DE</UserLocale>
```

## Related topics


[Microsoft-Windows-International-Core](microsoft-windows-international-core.md)

 

 







