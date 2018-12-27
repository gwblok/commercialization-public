---
title: DISM API Constants
description: DISM API Constants
ms.assetid: 4d4c29eb-aa68-496f-a4d4-4d8ff1e389ba

ms.date: 10/25/2017
ms.topic: article


---

# DISM API Constants


You can use the DISM API to install, uninstall, configure, and update Windows® features, packages, and drivers in a Windows image.

The constant values defined by the DISM API are described in this topic.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
DISM_ONLINE_IMAGE
DISM_MOUNT_READWRITE
DISM_MOUNT_READONLY
DISM_MOUNT_OPTIMIZE
DISM_MOUNT_CHECK_INTEGRITY
DISM_COMMIT_IMAGE
DISM_DISCARD_IMAGE
DISM_COMMIT_GENERATE_INTEGRITY
DISM_COMMIT_APPEND
DISM_COMMIT_MASK
```

## <span id="Constants"></span><span id="constants"></span><span id="CONSTANTS"></span>Constants


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>DISM_ONLINE_IMAGE</em></p></td>
<td><p>Indicates to the <a href="dismopensession-function.md" data-raw-source="[DismOpenSession Function](dismopensession-function.md)">DismOpenSession Function</a> that the online operating system, %windir%, should be associated to the <a href="dismsession.md" data-raw-source="[DISMSession](dismsession.md)">DISMSession</a> for servicing.</p></td>
</tr>
<tr class="even">
<td><p><em>DISM_MOUNT_READWRITE</em></p></td>
<td><p>Indicates to the <a href="dismmountimage-function.md" data-raw-source="[DismMountImage Function](dismmountimage-function.md)">DismMountImage Function</a> that the image should be mounted with both read and write access.</p></td>
</tr>
<tr class="odd">
<td><p><em>DISM_MOUNT_READONLY</em></p></td>
<td><p>Indicates to the <a href="dismmountimage-function.md" data-raw-source="[DismMountImage Function](dismmountimage-function.md)">DismMountImage Function</a> that the image should be mounted with read access only.</p></td>
</tr>
<tr class="even">
<td><p><em>DISM_MOUNT_OPTIMIZE</em></p></td>
<td><p>Indicates to the <a href="dismmountimage-function.md" data-raw-source="[DismMountImage Function](dismmountimage-function.md)">DismMountImage Function</a> that the image should be mounted with optimization. When the optimize option is used, only the top level of the file directory in the image will be mapped to the mount location. The first time that you access a file path that is not initially mapped, that branch of the directory will be mounted. As a result, there may be an increase in the time that is required to access a directory for the first time after mounting an image using the optimize option.</p></td>
</tr>
<tr class="odd">
<td><p><em>DISM_MOUNT_CHECK_INTEGRITY</em></p></td>
<td><p>Indicates to the <a href="dismmountimage-function.md" data-raw-source="[DismMountImage Function](dismmountimage-function.md)">DismMountImage Function</a> to set a flag on the image specifying whether the image is corrupted.</p></td>
</tr>
<tr class="even">
<td><p><em>DISM_COMMIT_IMAGE</em></p></td>
<td><p>Indicates to the <a href="dismcommitimage-function.md" data-raw-source="[DismCommitImage Function](dismcommitimage-function.md)">DismCommitImage Function</a> or the <a href="dismunmountimage-function.md" data-raw-source="[DismUnmountImage Function](dismunmountimage-function.md)">DismUnmountImage Function</a> that changes to the image should be saved.</p></td>
</tr>
<tr class="odd">
<td><p><em>DISM_DISCARD_IMAGE</em></p></td>
<td><p>Indicates to the <a href="dismcommitimage-function.md" data-raw-source="[DismCommitImage Function](dismcommitimage-function.md)">DismCommitImage Function</a> or the <a href="dismunmountimage-function.md" data-raw-source="[DismUnmountImage Function](dismunmountimage-function.md)">DismUnmountImage Function</a> that changes to the image should not be saved.</p></td>
</tr>
<tr class="even">
<td><p><em>DISM_COMMIT_GENERATE_INTEGRITY</em></p></td>
<td><p>Indicates to the <a href="dismcommitimage-function.md" data-raw-source="[DismCommitImage Function](dismcommitimage-function.md)">DismCommitImage Function</a> or the <a href="dismunmountimage-function.md" data-raw-source="[DismUnmountImage Function](dismunmountimage-function.md)">DismUnmountImage Function</a> to set a flag on the image specifying whether the image is corrupted.</p></td>
</tr>
<tr class="odd">
<td><p><em>DISM_COMMIT_APPEND</em></p></td>
<td><p>Indicates to the <a href="dismcommitimage-function.md" data-raw-source="[DismCommitImage Function](dismcommitimage-function.md)">DismCommitImage Function</a> or the <a href="dismunmountimage-function.md" data-raw-source="[DismUnmountImage Function](dismunmountimage-function.md)">DismUnmountImage Function</a> that changes to the image should be saved.</p></td>
</tr>
<tr class="even">
<td><p><em>DISM_COMMIT_MASK</em></p></td>
<td><p>Indicates to the <a href="dismunmountimage-function.md" data-raw-source="[DismUnmountImage Function](dismunmountimage-function.md)">DismUnmountImage Function</a> that all changes should be saved. This flag is equivalent to using DISM_COMMIT_IMAGE, DISM_COMMIT_GENERATE_INTEGRITY, and DISM_COMMIT_APPEND.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Requirements"></span><span id="requirements"></span><span id="REQUIREMENTS"></span>Requirements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Supported host platform</p></td>
<td><p>DISM API can be used on any operating system supported by the Windows® Assessment and Deployment Kit (Windows ADK). For more information, see the <a href="http://go.microsoft.com/fwlink/?LinkId=206587" data-raw-source="[Windows ADK Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587)">Windows ADK Technical Reference</a>.</p></td>
</tr>
<tr class="even">
<td><p>Supported image platform</p></td>
<td><p>Windows® 7, Windows Server 2008 R2, Windows 8, Windows Server® 2012</p></td>
</tr>
</tbody>
</table>

 

## <span id="related_topics"></span>Related topics


[DismOpenSession Function](dismopensession-function.md)

[DismMountImage Function](dismmountimage-function.md)

[DismCommitImage Function](dismcommitimage-function.md)

[DismUnmountImage Function](dismunmountimage-function.md)

 

 




