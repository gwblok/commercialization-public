---
title: ProtectYourPC
description: ProtectYourPC
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9c09e2f1-9cf5-45fd-80ed-21f1ba8584c5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# ProtectYourPC

`ProtectYourPC` specifies whether Express settings are used to:

* Personalize speech, typing, and inking input by sending contacts and calendar details, along with other associated input data to Microsoft.
* Let Windows and apps request the user's localization, including location history, and use the advertising ID to personalize experiences on the device.
* Turn on protection from malicious web content and use page prediction to pre-load sites in Windows browsers, which sends the browsing history to Microsoft.
* Automatically connect to suggested open and shared networks.
* Send problem reports to Microsoft.

## Values

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>1</strong></p></td>
<td><p>Turns on Express settings.</p></td>
</tr>
<tr class="even">
<td><p><strong>2</strong></p></td>
<td><p>Turns on Express settings.</p></td>
</tr>
<tr class="odd">
<td><p><strong>3</strong></p></td>
<td><p>Turns off Express settings.</p></td>
</tr>
</tbody>
</table>

There is no default value. If a value is not set, the **Get going fast** page opens during setup.

## Valid Configuration Passes

oobeSystem

## Parent Hierarchy

[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OOBE](microsoft-windows-shell-setup-oobe.md) | **ProtectYourPC**

## Applies To

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example

The following XML example shows how to turn off Express settings.

```XML
<OOBE>
   <ProtectYourPC>3</ProtectYourPC>
</OOBE>
```

## Related topics

[OOBE](microsoft-windows-shell-setup-oobe.md)
[Automate OOBE](https://docs.microsoft.com/windows-hardware/customize/desktop/automate-oobe)
