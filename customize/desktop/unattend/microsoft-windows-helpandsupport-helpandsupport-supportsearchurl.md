---
title: SupportSearchURL
description: SupportSearchURL
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: cb9ed493-50bf-4d0e-ac0e-d571569e7323
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SupportSearchURL


**Note**  
In Windows 10, this setting and other [HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md) settings are deprecated because the Help component that they impact is being retired. Existing information in this topic is provided for reference only.

For more information on how OEMs can include their customer support contact information in the Contact Support App or Support Web page, see [OEMInformation](microsoft-windows-shell-setup-oeminformation.md).

 

`SupportSearchURL` specifies the URL that the system uses to display a search link on the page of search results. For example, when a user performs a search in **Help and Support**, a link to the Original Equipment Manufacturer's (OEM's) webpage appears at the bottom of the search results. When the user clicks this link, the default web browser opens the webpage.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>&lt;URL&gt;</em></p></td>
<td><p>Specifies the URL of a link to a support page. <em>&lt;URL&gt;</em> is a string.</p>
<p>The URL can include a placeholder variable named <code>{Query}</code> for the search query. If this variable is in the URL, the system replaces the variable with the user&#39;s search query before it sends the URL to the browser:</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md) | [HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md) | `SupportSearchURL`

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md).

## XML Example


The following example shows how to set a customized **Help and Support** page.

When a user searches on the **Help and Support** page for "email", the **Support** section of the **Search Results** pane displays results from the `http://www.fabrikam.com/support/search/?term=email` webpage.

```
<HelpAndSupport>
  <Logo>C:\Fabrikam\Logos\Logo.png</Logo>
  <LogoURL>http://www.fabrikam.com/support</LogoURL>
  <Manufacturer>Fabrikam</Manufacturer>
  <SupportSearchURL>http://www.fabrikam.com/support/search/?term={Query}</SupportSearchURL>
</HelpAndSupport>
```

## Related topics


[Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md)

 

 







