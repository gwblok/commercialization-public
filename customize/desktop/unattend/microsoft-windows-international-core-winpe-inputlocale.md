---
title: InputLocale
description: InputLocale
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 07ebbbb9-52f6-4786-8658-7ec07484b25d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# InputLocale


`InputLocale` specifies the input language and the input method for input devices, such as the keyboard layout. This setting is used by Windows Setup and Windows Deployment Services.

The input locale (also called input language) is a per-process setting that describes a language (for example, Greek) and an input method (for example, the keyboard).

Multiple input locales can be installed, and the user can switch between them. Users can add and remove input locales through the **Keyboard and Languages** tab of the **Region and Language** Control Panel.

For a list of supported languages, locales, and identifiers, see [Supported Language Packs and Default Settings](http://go.microsoft.com/fwlink/?LinkId=206622).

## Value


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Input_locale</em></p></td>
<td><p>Specifies the input language and the keyboard layout for a Windows installation.</p>
<p><em>Input_locale</em> can be one of two values:</p>
<ul>
<li><p>A language identifier. For example, to use the default keyboard layout for English (United States) that corresponds to the QWERTY keyboard, you can specify the value <strong>en-US</strong>.</p></li>
<li><p>A locale ID and keyboard layout represented as hexadecimal values. For example, for en-US, use <strong>0409:00000409</strong>. The first 0409 value represents the locale ID of the input language, and the second 00000409 value represents the keyboard layout.</p></li>
</ul>
<p>To specify more than one input locale and add support for more than one keyboard type, you can specify multiple values separated by semicolons. For example, you can specify <code>&lt;InputLocale&gt;en-US; fr-FR; es-ES&lt;/InputLocale&gt;</code> to add support for English (US), French (France), and Spanish (Spain) keyboards. The first value that is listed is used as the default keyboard.</p>
<p>The valid keyboard layouts that can be configured on a computer are listed in the <strong>HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Control\Keyboard Layouts</strong> registry key.</p>
<p></p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Parent Hierarchy


[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md) | **InputLocale**

## Valid Configuration Passes


windowsPE

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md).

## XML Example


The following example shows how to set the input locale to the English (United States) Dvorak keyboard.

```
<InputLocale>0409:00010409</InputLocale>
<SystemLocale>en-US</SystemLocale> 
<UILanguage>en-US</UILanguage> 
<UserLocale>en-US</UserLocale>
```

## Related topics


[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md)

[Microsoft-Windows-International-Core](microsoft-windows-international-core.md)

 

 







