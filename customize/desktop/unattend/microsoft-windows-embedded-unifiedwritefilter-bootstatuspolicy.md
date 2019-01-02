---
title: BootStatusPolicy
description: Specifies the display policy of Windows boot loader errors.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 77717FE2-8A5A-45FC-86F4-B2DE1DCD8084
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# BootStatusPolicy


Specifies the display policy of Windows boot loader errors.

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
<td><p>DisplayAllFailures</p></td>
<td><p>Display all failures in the <strong>Windows Error Recovery</strong> window.</p></td>
</tr>
<tr class="even">
<td><p>IgnoreAllFailures</p></td>
<td><p>Ignore all boot failures and start Windows normally.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="odd">
<td><p>IgnoreShutdownFailures</p></td>
<td><p>Display only boot failures in the <strong>Windows Error Recovery</strong> window.</p></td>
</tr>
<tr class="even">
<td><p>IgnoreBootFailures</p></td>
<td><p>Display only shutdown failures in the <strong>Windows Error Recovery</strong> window.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md) | **BootStatusPolicy**

## Valid Configuration Passes


specialize

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md).

## XML example


```
<settings pass="specialize">
    <component name="Microsoft-Windows-Embedded-UnifiedWriteFilter" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
        <BootStatusPolicy>IgnoreShutdownFailures</BootStatusPolicy>
    </component>
</settings>
```

 

 






