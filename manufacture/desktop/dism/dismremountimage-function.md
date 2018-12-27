---
title: DismRemountImage function
description: Remounts a previously mounted Windows image from the .wim or .vhd file.
ms.assetid: 3cfbff39-569c-456e-b0ff-dd762e9c915f
keywords: DismRemountImage function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismRemountImage
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismRemountImage function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Remounts a previously mounted Windows image from the .wim or .vhd file at the path specified by *MountPath*. Use [**DismOpenSession**](dismopensession-function.md) to associate the image with a [DismSession](dismsession.md) after it is remounted.

You can use the **DismRemountImage** function when the image is in the **DismMountStatusNeedsRemount** state, as described by the [DismMountStatus](dismmountstatus-enumeration.md) enumeration. The image may enter this state if it is mounted and then a reboot occurs.

Syntax
---

```
HRESULT WINAPI DismRemountImage(
  _In_ PCWSTR MountPath
);
```

Parameters
-------

*MountPath* \[in\]  
A relative or absolute path to the mount directory of the image.

Return value
---------

A relative or absolute path to the mount directory of the image.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK; 
DismSession* Session = NULL; 
hr = DismRemountImage(L"C:\\Mount\\");
```

## <span id="Requirements"></span><span id="requirements"></span><span id="REQUIREMENTS"></span>Requirements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Supported host platforms for .wim files:</p></td>
<td><p>DISM API can be used on any operating system supported by the Windows® Assessment and Deployment Kit (Windows ADK). For more information, see the <a href="http://go.microsoft.com/fwlink/?LinkId=206587" data-raw-source="[Windows ADK Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587)">Windows ADK Technical Reference</a>.</p></td>
</tr>
<tr class="even">
<td><p>Supported host platforms for .vhd files:</p></td>
<td><p>Windows 7, Windows Server 2008 R2, Windows PE 3.0, Windows 8, Windows Server 2012, Windows Preinstallation Environment (Windows PE) 4.0, Windows 8.1, Windows Server 2012 R2, Windows 10, Windows Server 2016</p></td>
</tr>
</tbody>
</table>

 

Requirements
---------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Minimum supported client</p></td>
<td><p>Windows 7 [desktop apps only]</p></td>
</tr>
<tr class="even">
<td><p>Minimum supported server</p></td>
<td><p>Windows Server 2008 R2 [desktop apps only]</p></td>
</tr>
<tr class="odd">
<td><p>Header</p></td>
<td>DismAPI.h</td>
</tr>
<tr class="even">
<td><p>Library</p></td>
<td>DismAPI.lib</td>
</tr>
<tr class="odd">
<td><p>DLL</p></td>
<td>DismAPI.dll</td>
</tr>
</tbody>
</table>

## <span id="see_also"></span>See also


[**DismMountImage**](dismmountimage-function.md)

[**DismUnmountImage**](dismunmountimage-function.md)

[DismMountStatus](dismmountstatus-enumeration.md)

 

 




