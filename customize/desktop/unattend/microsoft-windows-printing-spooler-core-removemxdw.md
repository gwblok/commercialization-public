---
title: RemoveMXDW
description: RemoveMXDW
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9ea5a109-d6df-4bcc-b695-c0f4645e8236
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# RemoveMXDW


The `RemoveMXDW` setting is used to remove the Microsoft XPS Document Writer (MXDW) print queue and driver package from a Windows installation.

**To create a Windows image without the MXDW print queue and driver package**

1.  In your answer file, set `RemoveMXDW` to **1**.

2.  In your answer file, remove the MXDW print queue and driver package installation files. To do this, add the Microsoft-Windows-Printing-XPSServices-Package package. In the **Actions** field, select **Remove**. 

3.  Install Windows using your answer file.

4.  After installation, open the Printers folder to completely remove the files.

5.  Run the Sysprep tool, and then recapture the Windows image.

This setting has no effect on Server Core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>0</strong></p></td>
<td><p>The MXDW print queue and driver packages are not removed during Windows installation.</p></td>
</tr>
<tr class="even">
<td><p><strong>1</strong></p></td>
<td><p>The MXDW print queue and driver packages are removed during Windows installation.</p>
<p>After the files are removed, you will be unable to reinstall the Microsoft XPS Document Writer print queue.</p>
<p></p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Printing-Spooler-Core](microsoft-windows-printing-spooler-core.md) | **RemoveMXDW**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Printing-Spooler-Core](microsoft-windows-printing-spooler-core.md).

## XML Example


The following XML output shows how to remove the XPS Document Writer print queue and driver package.

```
<RemoveMXDW>1</RemoveMXDW>
```

## Related topics


[Microsoft-Windows-Printing-Spooler-Core](microsoft-windows-printing-spooler-core.md)

 

 







