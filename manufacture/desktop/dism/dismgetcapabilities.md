---
title: DismGetCapabilities function
description: Gets DISM capabilities.
ms.assetid: CB9E831C-A31B-4A46-91ED-756CE6F19B58
keywords: DismGetCapabilities function

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismGetCapabilities
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismGetCapabilities function


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Gets DISM capabilities.

Syntax
---

```
HRESULT WINAPI DismGetCapabilities(
  _In_ DismSession    Session,
  _In_ DismCapability Capability,
  _In_ UINT           Count
);
```

Parameters
-------

*Session* \[in\]  
A valid [DismSession](dismsession.md). The DismSession must be associated with an image. You can associate a session with an image by using the [**DismOpenSession**](dismopensession-function.md).

*Capability* \[in\]  
The name of the specified capability.

*Count* \[in\]  
Pointer that will receive the info of capability.

Return value
---------

Returns `S_OK` on success.

## <span id="Example"></span><span id="example"></span><span id="EXAMPLE"></span>Example


```
HRESULT hr = S_OK;
DismCapability* Capability;
UINT CapabilityCount;

hr = DismGetCapabilities(Session, &amp;Capability, &amp;CapabilityCount); 
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
<td><p>Windows 10, Windows Server 2016</p></td>
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
<td><p>Windows 10 [desktop apps only]</p></td>
</tr>
<tr class="even">
<td><p>Minimum supported server</p></td>
<td><p>Windows Server 2016 [desktop apps only]</p></td>
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

[**DismEnableFeature**](dismenablefeature-function.md)

[**DismGetPackages**](dismgetpackages-function.md)

[**DismGetPackageInfo**](dismgetpackageinfo-function.md)

[**DismRemovePackage**](dismremovepackage-function.md)

[DismPackage](dismpackagefeaturestate-enumeration.md)

[DismPackageInfo](dismpackageinfo-structure.md)

DismPackageFeatureState
 

 




