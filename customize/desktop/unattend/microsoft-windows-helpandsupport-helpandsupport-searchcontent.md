---
title: SearchContent
description: SearchContent
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 18361b84-7a5e-4d13-ba5e-d835b98b42ef
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SearchContent


**Note**  
In Windows 10, this setting and other [HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md) settings are deprecated because the Help component that they impact is being retired. Existing information in this topic is provided for reference only.

For more information on how OEMs can include their customer support contact information in the Contact Support App or Support Web page, see [OEMInformation](microsoft-windows-shell-setup-oeminformation.md).



`SearchContent` specifies whether the Original Equipment Manufacturer (OEM) or organization has provided offline Help content that **Help and Support** must return in search results.

When an end user performs a search in **Help and Support**, Windows searches for the OEM's offline Help content.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>When a user performs a search in <strong>Help and Support</strong>, Windows searches for matching Help content in offline Help files that the OEM provides.</p>
<div class="alert">
<strong>Note</strong><br/><p>For the results to appear, you must also set both the Microsoft-Windows-HelpAndSupport/<code>HelpAndSupport</code>/<a href="microsoft-windows-helpandsupport-helpandsupport-manufacturer.md" data-raw-source="[Manufacturer](microsoft-windows-helpandsupport-helpandsupport-manufacturer.md)">Manufacturer</a> value to <strong>true</strong> and the Microsoft-Windows-Shell-Setup/<code>OEMInformation</code>/<a href="microsoft-windows-shell-setup-oeminformation-helpcustomized.md" data-raw-source="[HelpCustomized](microsoft-windows-shell-setup-oeminformation-helpcustomized.md)">HelpCustomized</a> value to <strong>true</strong>.</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>When a user performs a search in <strong>Help and Support</strong>, Windows searches for Help content only in the data store for Windows Help files.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>



## Valid Configuration Passes


oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md) | [HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md) | **SearchContent**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md).

## XML Example


The following example shows how to configure Windows to perform **Help and Support** searches from both Windows and offline Help files that the OEM or organization provides when the computer is offline.

```
<Manufacturer>Fabrikam</Manufacturer>
<SearchContent>true</SearchContent>
```

## Related topics


[Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md)











