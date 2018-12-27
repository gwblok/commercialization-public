---
title: DismApplyUnattend function
description: Applies an unattended answer file to a Windows® image.
ms.assetid: e1d9903f-2b12-421b-8802-55a3e770ca1f
keywords: DismApplyUnattend function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismApplyUnattend
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismApplyUnattend function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Applies an unattended answer file to a Windows® image.

Syntax
---

```
HRESULT WINAPI DismApplyUnattend(
  _In_ DismSession Session,
  _In_ PCWSTR      UnattendFile,
  _In_ BOOL        SingleSession
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*UnattendFile* \[in\]  
A relative or absolute path to the answer file that will be applied to the image.

*SingleSession* \[in\]  
A Boolean value that specifies whether the packages that are listed in an answer file will be processed in a single session or in multiple sessions.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><code>TRUE</code></p></td>
<td><p>The unattended answer file will be processed in a single session.</p></td>
</tr>
<tr class="even">
<td><p><code>FALSE</code></p></td>
<td><p>All of the packages that are listed in the answer file will be processed in multiple sessions.</p></td>
</tr>
</tbody>
</table>

 

Return value
---------

Returns `S_OK` on success.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


When you use DISM to apply an answer file to an image, the unattended settings in the **offlineServicing** configuration pass are applied to the Windows image. For more information, see [Unattended Servicing Command-Line Options](http://go.microsoft.com/fwlink/?LinkId=200973).

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
hr = DismApplyUnattend(Session, "C:\test\unattend.xml", TRUE);
```

## <span id="Requirements"></span><span id="requirements"></span><span id="REQUIREMENTS"></span>Requirements


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Supported host platforms:</p></td>
<td><p>DISM API can be used on any operating system supported by the Windows® Assessment and Deployment Kit (Windows ADK). For more information, see the <a href="http://go.microsoft.com/fwlink/?LinkId=206587" data-raw-source="[Windows ADK Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587)">Windows ADK Technical Reference</a>.</p></td>
</tr>
<tr class="even">
<td><p>Supported image platforms:</p></td>
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


[**DismAddDriver**](dismadddriver-function.md)

[**DismAddPackage**](dismaddpackage-function.md)

[**DismEnableFeature**](dismenablefeature-function.md)

 

 




