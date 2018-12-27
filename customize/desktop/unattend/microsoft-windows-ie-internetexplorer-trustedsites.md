---
title: TrustedSites
description: TrustedSites
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8c995bab-19c2-42e6-a142-a9921a6fe467
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# TrustedSites


`TrustedSites` specifies the Uniform Resource Locator (URL) for Internet sites whose content can be trusted by administrators and users for whom Internet Explorer Enhanced Security Configuration (ESC) is enabled.

When Internet Explorer ESC is enabled, it reduces the exposure of your server to potential security attacks from Web pages that do not belong to the Trusted sites zone.

For more information, see [Microsoft-Windows-IE-ESC](microsoft-windows-ie-esc.md).

**Note**  
This setting is applicable only for Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 and Windows Server 2008. The Internet Explorer ESC must also be enabled for this setting to apply.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path_to_url</em></p></td>
<td><p>Specifies the fully qualified path to the URL of each Internet site. You can add multiple sites, using semi-colons as the separator. <em>Path_to_url</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **TrustedSites**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output specifies the fully qualified URLs.

```
<TrustedSites>http://www.fabrikam.com;http://www.contoso.com</TrustedSites>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

[LocalIntranetSites](microsoft-windows-ie-internetexplorer-localintranetsites.md)

 

 







