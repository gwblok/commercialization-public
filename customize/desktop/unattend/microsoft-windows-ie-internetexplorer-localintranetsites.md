---
title: LocalIntranetSites
description: LocalIntranetSites
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: def29dae-ec93-4fa1-bf54-e47caa53fa6a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# LocalIntranetSites


`LocalIntranetSites` specifies the URL for local intranet sites whose content can be trusted by administrators and users for whom Internet Explorer Enhanced Security Configuration (ESC) is enabled.

When Internet Explorer ESC is enabled, it reduces the exposure of your server to potential security attacks from Web pages that do not belong to the local intranet zone.

For more information, see [Microsoft-Windows-IE-ESC](microsoft-windows-ie-esc.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path_to_url</em></p></td>
<td><p>Specifies the path to the URL of each local intranet site. You can add multiple sites by using semicolons as the separator. <em>Path_to_url</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **LocalIntranetSites**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output specifies the URLs of local intranet sites with trusted content.

```
<LocalIntranetSites>http://internal;http://internal2</LocalIntranetSites>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

[TrustedSites](microsoft-windows-ie-internetexplorer-trustedsites.md)

 

 







