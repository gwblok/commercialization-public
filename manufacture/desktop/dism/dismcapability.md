---
title: DismCapability structure
description: Describes capability basic information.
ms.assetid: 3916441C-BF6B-48F2-85A8-6943A3689A5D
keywords: DismCapability structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismCapability
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---


# DismCapability structure


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Describes capability basic information.

Syntax
---

```
typedef struct _DismCapability {
  PCWSTR                  Name;
  DismPackageFeatureState State;
} DismCapability;
```

Members
----

**Name**  
The manufacturer name of the driver.

**State**  
A hardware description of the driver.

## <span id="Remarks"></span><span id="remarks"></span><span id="REMARKS"></span>Remarks


To retrieve more information about a particular capability, use the [**DismGetCapabilityInfo**](dismgetcapabilityinfo.md) function.

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
</tbody>
</table>

## <span id="see_also"></span>See also


[**DismGetCapabilityInfo**](dismgetcapabilityinfo.md)

 

 




