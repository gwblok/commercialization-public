---
title: LogPath
description: LogPath
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4c9ea64e-a02d-4066-bc4c-5c5b9a8a9056
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# LogPath


`LogPath` specifies the path of the log file to use during the Windows Preinstallation Environment (Windows PE) phase of installation. This log file is used only to log the events related to configuring Windows PE and not a regular operating system. (Windows PE is a minimal operating system designed to prepare a computer for Windows installation.) The log files used to configure a regular operating system, available in the %WINDIR%\\panther or $windows.~bt\\sources\\panther directories, cannot be changed.

The `LogPath` setting must be the fully qualified, non-UNC path to a directory on a fixed disk of the local computer.

This setting refers to a directory where the log files are written, rather than an individual log file. These log files contain details for settings related to the windowsPE configuration pass.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path_to_log_file</em></p></td>
<td><p>Specifies the fully qualified, non-UNC path to a directory on a fixed disk of the local computer.</p>
<p>For example, to create log files in a Log folder at the root of the C drive, set this value to <strong>C:\Log</strong>.</p>
<p><em>Path_to_log_file</em> is a string, with a maximum length of 259 characters.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | **LogPath**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to set the log path.

```
<LogPath>C:\Log</LogPath>
```

## Related topics


[microsoft-windows-setup-](microsoft-windows-setup.md)

 

 







