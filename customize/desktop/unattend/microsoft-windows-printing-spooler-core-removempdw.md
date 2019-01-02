---
title: RemoveMPDW
description: You can use the RemoveMPDW setting to remove the Microsoft Print to PDF print queue and driver package from a Windows installation.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2B4E7891-E464-46B4-9E69-22F9BD185716
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# RemoveMPDW


Starting with Windows 10, the OS includes support for the Microsoft Print to PDF feature. You can use the `RemoveMPDW` setting to remove the Microsoft Print to PDF print queue and driver package from a Windows installation.

Microsoft Print to PDF ships as an optional feature and is installed by default. OEMs and IT administrators can configure the Windows installation to remove this feature.

**To create a Windows image without the Microsoft Print to PDF print queue and driver package**

1.  In your answer file, set `RemoveMPDW` to 1.

2.  In your answer file, remove the Microsoft Print to PDF print queue and driver package installation files. To do this, add the Microsoft-Windows-Printing-PDFServices-Package package. In the **Actions** field, select **Remove**.

3.  Install Windows using your answer file.

4.  After installation, open the Printers folder to completely remove the files.

5.  Run the Sysprep tool, and then recapture the Windows image.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>0</p></td>
<td><p>The Microsoft Print to PDF print queue and driver packages are not removed during Windows installation.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>The Microsoft Print to PDF print queue and driver packages are removed during Windows installation.</p>
<p>After the files are removed, you will be unable to reinstall the Microsoft Print to PDF print queue.</p>
<p></p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Printing-Spooler-Core](microsoft-windows-printing-spooler-core.md) | **RemoveMPDW**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Printing-Spooler-Core](microsoft-windows-printing-spooler-core.md).

## XML Example


The following XML output shows how to remove the Microsoft Print to PDF print queue and driver package.

```
<RemoveMPDW>1</RemoveMPDW>
```

## Related topics


[Microsoft-Windows-Printing-Spooler-Core](microsoft-windows-printing-spooler-core.md)

 

 







