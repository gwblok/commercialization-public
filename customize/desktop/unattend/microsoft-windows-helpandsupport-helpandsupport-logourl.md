---
title: LogoURL
description: LogoURL
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f52c164e-1af0-461a-8022-e8821c55ee7e
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# LogoURL


**Note**  
In Windows 10, this setting and other [HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md) settings are deprecated because the Help component that they impact is being retired. Existing information in this topic is provided for reference only.

For more information on how OEMs can include their customer support contact information in the Contact Support App or Support Web page, see [OEMInformation](microsoft-windows-shell-setup-oeminformation.md).

 

`LogoURL` specifies a link to an Original Equipment Manufacturer's (OEM's) webpage, a Help topic, or an executable file. This link appears on the **Help and Support** home page. When an end user clicks the logo of the OEM or organization, the corresponding page opens.

The `LogoURL` setting is used together with the [Logo](microsoft-windows-helpandsupport-helpandsupport-logo.md) setting. When both settings are present, the logo appears and the link is active.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>&lt;Path&gt;</em></p></td>
<td><p>Specifies the path of the support page for the OEM or organization. <em>&lt;Path&gt;</em> is a string.</p>
<p>To create a link to a program, use this format: <code>shortcut:&lt;PathToExeFile&gt;</code></p>
<p>To create a link to a page in <strong>Help and Support</strong>, use this format: <code>mshelp://OEM/?id=&lt;TopicGUID&gt;</code></p>
<p>To create a link to a webpage, use this format: <code>http://&lt;WebpageAddress&gt;</code></p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md) | [HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md) | `LogoURL`

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md).

## XML Example


The following example shows how to set a customized **Help and Support** home page. When a user clicks the Fabrikam logo on the **Help and Support** home page, the http://www.fabrikam.com/support webpage opens.

```
<HelpAndSupport>
  <Logo>%systemdrive%\Fabrikam\Logos\Logo.png</Logo>
  <LogoURL>http://www.fabrikam.com/support</LogoURL>
  <Manufacturer>Fabrikam</Manufacturer>
</HelpAndSupport>
```

## Related topics


[Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md)

[Logo](microsoft-windows-helpandsupport-helpandsupport-logo.md)

 

 







