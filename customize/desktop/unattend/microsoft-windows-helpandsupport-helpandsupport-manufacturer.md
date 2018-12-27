---
title: Manufacturer
description: Manufacturer
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: be7925b7-2ddc-4ca1-8757-d34dd93f5f93
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Manufacturer


**Note**  
In Windows 10, this setting and other [HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md) settings are deprecated because the Help component that they impact is being retired. Existing information in this topic is provided for reference only.

For more information on how OEMs can include their customer support contact information in the Contact Support App or Support Web page, see [OEMInformation](microsoft-windows-shell-setup-oeminformation.md).

 

`Manufacturer` specifies the name of the Original Equipment Manufacturer (OEM).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>&lt;Manufacturer_name&gt;</em></p></td>
<td><p>Specifies the name of the OEM. <em>&lt;Manufacturer_name&gt;</em> is a string that has a maximum length of 256 characters.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md) | [HelpAndSupport](microsoft-windows-helpandsupport-helpandsupport.md) | **Manufacturer**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md).

## XML Example


The following example shows how to set a customized **Help and Support** home page. The title of the **Help and Support** home page includes the Fabrikam company name. For example, the page title may be **Fabrikam Help and Support**.

```
<HelpAndSupport>
  <Logo>C:\Fabrikam\Logos\Logo.png</Logo>
  <LogoURL>http://www.fabrikam.com/support</LogoURL>
  <Manufacturer>Fabrikam</Manufacturer>
</HelpAndSupport>
```

## Related topics


[Microsoft-Windows-HelpAndSupport](microsoft-windows-helpandsupport.md)

 

 







