---
title: FileExceptionsUserDefined
description: Specifies the full path of the files or folders on a protected volume to exclude from filtering by UWF.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 207A78BE-9718-4DC6-B2CD-D957FCFF812A
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# FileExceptionsUserDefined


Specifies the full path of the files or folders on a protected volume to exclude from filtering by UWF.

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
<td><p><em>FileExceptions</em></p></td>
<td><p>Specifies the full path of the files or folders on a protected volume to exclude from filtering by UWF.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md) | [ProtectedVolumeList](microsoft-windows-embedded-unifiedwritefilter-protectedvolumelist.md) | [ProtectedVolumeEntry](microsoft-windows-embedded-unifiedwritefilter-protectedvolumelist-protectedvolumeentry.md) | **FileExceptionsUserDefined**

## Valid Configuration Passes


specialize

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-UnifiedWriteFilter](microsoft-windows-embedded-unifiedwritefilter.md).

## XML example


```
<settings pass="specialize">
    <component name="Microsoft-Windows-Embedded-UnifiedWriteFilter" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
        <ProtectedVolumeList>
            <ProtectedVolumeEntry wcm:action="add">
                <FileExceptionsUserDefined>C:\User\Test\Test.log C:\User\Log</FileExceptionsUserDefined>
            </ProtectedVolumeEntry>
        </ProtectedVolumeList>
    </component>
</settings>
```

 

 






