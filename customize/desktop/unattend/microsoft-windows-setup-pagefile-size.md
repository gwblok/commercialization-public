---
title: Size
description: Size
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 290c7bde-7570-4d3b-a724-36b6a0779c24
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Size


`Size` specifies the size, in megabytes, of the page file to create for [PageFile](microsoft-windows-setup-pagefile.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>size_of_the_page_file_in_megabytes</em></p></td>
<td><p>Specifies the size of the page file to create, in megabytes.</p>
<p>If this value is set, but there is no path specified to a page file, this value is applied to the default page file on the computer.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [PageFile](microsoft-windows-setup-pagefile.md) | **Size**

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

 

 







