---
title: Microsoft-Windows-HelpAndSupport
description: Microsoft-Windows-HelpAndSupport
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7d957ce8-fb2f-4484-bc17-36fef89d368a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/17/2017
ms.topic: article


---
# Microsoft-Windows-HelpAndSupport

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
<td><p><a href="microsoft-windows-helpandsupport-helpandsupport.md" data-raw-source="[HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md)">HelpAndSupport</a></p></td>
<td><p>Contains settings to specify OEM information for a customized <strong>Help and Support</strong> page.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

specialize

## Applies To


To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## XML Example


The following example shows how to set a customized **Help and Support** page. The home page is branded with the Fabrikam logo. When the user clicks the logo, the default browser starts and the URL bar is prepopulated with http://www.fabrikam.com.

```
<HelpAndSupport>
  <Logo>C:\Fabrikam\Logos\Logo.png</Logo>
  <LogoURL>http://www.fabrikam.com/support</LogoURL>
  <Manufacturer>Fabrikam</Manufacturer>
  <SupportSearchURL>http://www.fabrikam.com/support/search/?term={Query}</SupportSearchURL>
  <TileColor>65280</TileColor>
</HelpAndSupport>
```

## Related topics


[Components](components-b-unattend.md)

[OEMInformation](microsoft-windows-shell-setup-oeminformation.md)

 

 







