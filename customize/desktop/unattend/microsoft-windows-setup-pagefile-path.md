---
title: Path
description: Path
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e03978f5-a516-4fb0-b501-df2f5c30f345
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Path


`Path` specifies the path of the page file to create for [PageFile](microsoft-windows-setup-pagefile.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>path_to_page_file</em></p></td>
<td><p>Specifies the fully qualified path on a fixed disk of the page file to create.</p>
<p>You can use predefined system environment variables to specify the path to the page file. For example, to create a page file in the Windows directory on the destination computer, use <strong>%WINDIR%</strong> as the value.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [PageFile](microsoft-windows-setup-pagefile.md) | **Path**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to create a page file.

```
<PageFile>
   <Path>%WINDIR%\MyPagefile.sys</Path>
   <Size>512</Size>
</PageFile>
```

## Related topics


[PageFile](microsoft-windows-setup-pagefile.md)

 

 







