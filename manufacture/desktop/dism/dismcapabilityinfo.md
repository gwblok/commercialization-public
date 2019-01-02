---
title: DismCapabilityInfo structure
description: Describes information about a capability.
ms.assetid: 05A13309-ADDD-4AEA-B8E2-D87D05541735
keywords: DismCapabilityInfo structure

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismCapabilityInfo
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismCapabilityInfo structure


\[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.\]

Describes information about a capability.

Syntax
---

```
typedef struct _DismCapabilityInfo {
  PCWSTR                  Name;
  DismPackageFeatureState State;
  PCWSTR                  DisplayName;
  PCWSTR                  Description;
  DWORD                   DownloadSize;
  DWORD                   InstallSize;
} DismCapabilityInfo;
```

Members
----

**Name**  
The name of the capability.

**State**  
The state of the capability.

**DisplayName**  
The display name of the capability.

**Description**  
The description of the capability.

**DownloadSize**  
The download size of the capability in bytes.

**InstallSize**  
The install size of the capability in bytes.

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


[**DismGetCapabilities**](dismgetcapabilities.md)

 

 




