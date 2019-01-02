---
title: TSCALPersisted
description: Specifies whether the Terminal Services Client Access Licensing (TSCAL) registry key is in the UWF exclusion list.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0606B988-E266-4FC9-A183-E234E2F97569
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# TSCALPersisted


Specifies whether the Terminal Services Client Access Licensing (TSCAL) registry key is in the UWF exclusion list.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>False</p></td>
<td><p>The TSCAL registry key is not in the UWF exclusion list.</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>The TSCAL registry key is in the UWF exclusion list.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md) | **TSCALPersisted**

## Valid Configuration Passes


specialize

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md).

## XML example


```
<settings pass="specialize">
    <component name="Microsoft-Windows-Embedded-UnifiedWriteFilter" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
        <TSCALPersisted>False</TSCALPersisted>
    </component>
</settings>
```

 

 






