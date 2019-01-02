---
title: CompatibilityViewDomains
description: CompatibilityViewDomains
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 484448a3-fb7b-480b-bfe4-6b94cef69a6d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# CompatibilityViewDomains


`CompatibilityViewDomains` controls the list of domains that will be rendered in Compatibility View mode. The administrator needs to list the domains manually.

In Compatibility View, Internet Explorer displays WWeb pages from the specified domain as they would be shown on an earlier version of Internet Explorer.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>domain_list</em></p></td>
<td><p>Specifies a list of domains to be rendered in Compatibility View mode.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | `CompatibilityViewDomains`

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output specifies how to render Web pages from the fabrikam.com and contoso.com domains in Compatibility View mode.

```
<CompatibilityViewDomains>www.fabrikam.com;www.contoso.com</CompatibilityViewDomains>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

[IntranetCompatibilityMode](microsoft-windows-ie-internetexplorer-intranetcompatibilitymode.md)

 

 







