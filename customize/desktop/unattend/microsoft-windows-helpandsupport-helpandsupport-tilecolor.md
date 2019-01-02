---
title: TileColor
description: TileColor
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3f962288-76b3-4976-9b5a-29e19ebcf6a5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# TileColor


**Note**  
In Windows 10, this setting and other [HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md) settings are deprecated because the Help component that they impact is being retired. Existing information in this topic is provided for reference only.

For more information on how OEMs can include their customer support contact information in the Contact Support App or Support Web page, see [OEMInformation](microsoft-windows-shell-setup-oeminformation.md).

 

`TileColor` specifies the RGB background color of the tile for the Original Equipment Manufacturer (OEM) or organization on the **Help and Support** home page. The [Logo](microsoft-windows-helpandsupport-helpandsupport-logo.md) setting specifies the OEM tile.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>&lt;Integer&gt;</em></p></td>
<td><p>Specifies the integer representation of the background color of the OEM tile on the <strong>Help and Support</strong> home page by using the RGB color model.</p>
<p>The RGB color model is used for specifying colors. This model specifies the intensity of red, green, and blue on a scale of 0 to 255. A 0 indicates the minimum intensity. You can use this formula to convert the settings of the three colors to a single integer value:</p>
<p>RGB value = Red + (Green<em>256) + (Blue</em>256*256)</p>
<p>For more information and examples, see <a href="http://go.microsoft.com/fwlink/?LinkId=140169" data-raw-source="[RGB Color Model](http://go.microsoft.com/fwlink/?LinkId=140169)">RGB Color Model</a>.</p>
<p>For the background color to appear, you must also configure the TileColor setting, the <a href="microsoft-windows-helpandsupport-helpandsupport-logo.md" data-raw-source="[Logo](microsoft-windows-helpandsupport-helpandsupport-logo.md)">Logo</a> setting, and the <a href="microsoft-windows-helpandsupport-helpandsupport-manufacturer.md" data-raw-source="[Manufacturer](microsoft-windows-helpandsupport-helpandsupport-manufacturer.md)">Manufacturer</a> setting.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md) | [HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md) | **TileColor**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md).

## XML Example


The following example shows how to set the background color of the OEM tile on the **Help and Support** page to green.

```
<Manufacturer>Fabrikam</Manufacturer>
<Logo>C:\Windows\Fabrikam\FabrikamLogo.png</Logo>
<LogoURL>http://www.fabrikam.com/support</LogoURL>
<TileColor>65280</TileColor>
```

## Related topics


[Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md)

[Logo](microsoft-windows-helpandsupport-helpandsupport-logo.md)

[Manufacturer](microsoft-windows-helpandsupport-helpandsupport-manufacturer.md)

 

 







