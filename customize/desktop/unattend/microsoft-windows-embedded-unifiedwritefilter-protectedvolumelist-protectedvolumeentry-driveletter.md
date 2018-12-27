---
title: DriveLetter
description: Specifies the drive letter of a volume protected by UWF.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 40A1EE52-8D7B-48F9-AC0B-93A72536E0FC
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# DriveLetter

Specifies the drive letter of a volume protected by UWF.

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
<td><p><em>DriveLetter</em></p></td>
<td><p>Specifies the drive letter of a volume protected by UWF.</p></td>
</tr>
</tbody>
</table>

## Parent Hierarchy

[Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md) | [ProtectedVolumeList](microsoft-windows-embedded-unifiedwritefilter-protectedvolumelist.md) | [ProtectedVolumeEntry](microsoft-windows-embedded-unifiedwritefilter-protectedvolumelist-protectedvolumeentry.md) | **DriveLetter**

## Valid Configuration Passes

specialize

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md).

## XML example

```XML
<settings pass="specialize">
    <component name="Microsoft-Windows-Embedded-UnifiedWriteFilter" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
        <ProtectedVolumeList>
            <ProtectedVolumeEntry wcm:action="add">
                <DriveLetter>C:</DriveLetter>
            </ProtectedVolumeEntry>
        </ProtectedVolumeList>
    </component>
</settings>
```
