---
title: HelpAndSupport
description: HelpAndSupport
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 01f5aa96-b47b-40c0-a3bf-0a890407797b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# HelpAndSupport

> [!Important]
> In Windows 10, the [HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md) settings are deprecated because the Help component that they impact is being retired. Existing information about the HelpAndSupport settings are provided for reference only.
> Windows 10 offers a new user support system, the Get Help app. For more information, see [Customize the Get Help app](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/customize-get-help-app).


In Windows 10, the OS disables the help components that shipped in Windows 8 and Windows 8.1 including the Help and Support Windows desktop application (HelpPane.exe). HelpPane.exe will continue to exist in the box, but calls to its interfaces will result in one of two outcomes:

-   If the user is offline, the OS launches the Getting Started app.
-   If the user is online, the OS opens a browser instance and redirects the browser to an online topic.

For more information on how OEMs can include their customer support contact information in the Contact Support App or Support Web page, see [OEMInformation](microsoft-windows-shell-setup-oeminformation.md).

## Child Elements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="microsoft-windows-helpandsupport-helpandsupport-logo.md" data-raw-source="[Logo](microsoft-windows-helpandsupport-helpandsupport-logo.md)">Logo</a></p></td>
<td><p>Specifies the path of an image file that contains the logo of the OEM or organization.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-helpandsupport-helpandsupport-logourl.md" data-raw-source="[LogoURL](microsoft-windows-helpandsupport-helpandsupport-logourl.md)">LogoURL</a></p></td>
<td><p>Specifies the URL for a support page for the OEM or organization.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-helpandsupport-helpandsupport-manufacturer.md" data-raw-source="[Manufacturer](microsoft-windows-helpandsupport-helpandsupport-manufacturer.md)">Manufacturer</a></p></td>
<td><p>Specifies the name of the OEM.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-helpandsupport-helpandsupport-searchcontent.md" data-raw-source="[SearchContent](microsoft-windows-helpandsupport-helpandsupport-searchcontent.md)">SearchContent</a></p></td>
<td><p>Specifies whether the OEM or organization has provided offline Help content that the system must return in the search results.</p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-helpandsupport-helpandsupport-supportsearchurl.md" data-raw-source="[SupportSearchURL](microsoft-windows-helpandsupport-helpandsupport-supportsearchurl.md)">SupportSearchURL</a></p></td>
<td><p>Specifies the URL that the system uses to display a search link on the page of search results.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-helpandsupport-helpandsupport-tilecolor.md" data-raw-source="[TileColor](microsoft-windows-helpandsupport-helpandsupport-tilecolor.md)">TileColor</a></p></td>
<td><p>Specifies the RGB background color of the tile for the OEM or organization on the <strong>Help and Support</strong> home page.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md) | `HelpAndSupport`

## XML Example


The following example shows how to set values for customizing the **Help and Support** user interface. This example customizes the **Help and Support** page to have a blue (16711680) OEM tile that includes the Fabrikam logo. When a user clicks the tile, the default Web browser opens http://www.fabrikam.com/support. When a user performs a search while offline, the system returns the matching offline Fabrikam topics in the **Help and Support** search results. When a user performs a search while online, the system returns the matching Fabrikam topics from the http://www.fabrikam.com/support/search page in the **Help and Support** search results. The Fabrikam name appears on the search-results page and on the OEM tile on the home page.

```
<HelpAndSupport>
  <Logo>C:\Fabrikam\Logos\Logo.bmp</Logo>
  <LogoURL>http://www.fabrikam.com/support</LogoURL>
  <Manufacturer>Fabrikam</Manufacturer>
  <SearchContent>true</SearchContent>
  <SupportSearchURL>http://www.fabrikam.com/support/search/?term={Query}</SupportSearchURL>
  <TileColor>16711680</TileColor>
</HelpAndSupport>
```

## Related topics


[Components](components-b-unattend.md)

[OEMInformation](microsoft-windows-shell-setup-oeminformation.md)

 

 







