---
title: UserLocale
description: UserLocale
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f08e068f-f8b8-4f8c-85e9-057e195b76d2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# UserLocale


`UserLocale` specifies the per-user settings that are used for formatting dates, times, currency, and numbers in a Windows installation.

This setting is used during Windows Setup and Windows Deployment Services.

Users can change this value on a running Windows installation by using the **Region and Language Options** Control Panel.

For a list of supported languages, locales, and identifiers, see [Available Language Packs](http://go.microsoft.com/fwlink/p/?linkid=200318).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>User_locale</em></p></td>
<td><p>Specifies the user locale to use during Windows Setup or Windows Deployment Services.</p>
<p>The <em>User_locale</em> string is based on the language-tagging conventions of RFC 3066.The pattern <em>language</em>-<em>region</em> is used, where <em>language</em> is a language code and <em>region</em> is a country or region identifier (for example, <strong>en-US</strong>, <strong>fr-FR</strong>, or <strong>es-ES</strong>).</p>
<p>This value is not case-sensitive.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Parent Hierarchy


[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md) | **UserLocale**

## Valid Configuration Passes


windowsPE

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md).

## XML Example


The following example shows how to set the user locale to Japanese (Japan).

```
<InputLocale>0411:00000411</InputLocale> 
<SystemLocale>ja-JP</SystemLocale> 
<UILanguage>ja-JP</UILanguage> 
<UserLocale>ja-JP</UserLocale>
```

## Related topics


[Available Language Packs](http://go.microsoft.com/fwlink/p/?linkid=200318)

[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md)

 

 







