---
title: DismDriverSignature enumeration
description: Specifies the signature status of a driver.
ms.assetid: f93b49b6-e561-4155-8de4-5e4b8b561c6d
keywords: DismDriverSignature enumeration

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismDriverSignature
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismDriverSignature enumeration


Specifies the signature status of a driver.

Syntax
---

```
typedef enum DismDriverSignature { 
  DismDriverSignatureUnknown   = 0,
  DismDriverSignatureUnsigned  = 1,
  DismDriverSignatureSigned    = 2
} DismDriverSignature;
```

Constants
------

<span id="DismDriverSignatureUnknown"></span><span id="dismdriversignatureunknown"></span><span id="DISMDRIVERSIGNATUREUNKNOWN"></span>**DismDriverSignatureUnknown**  
The signature status of the driver is unknown. DISM only checks for a valid signature for boot-critical drivers.

<span id="DismDriverSignatureUnsigned"></span><span id="dismdriversignatureunsigned"></span><span id="DISMDRIVERSIGNATUREUNSIGNED"></span>**DismDriverSignatureUnsigned**  
The driver is unsigned.

<span id="DismDriverSignatureSigned"></span><span id="dismdriversignaturesigned"></span><span id="DISMDRIVERSIGNATURESIGNED"></span>**DismDriverSignatureSigned**  
The driver is signed.

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
</tbody>
</table>

## <span id="see_also"></span>See also


[**DismDriver**](dismdriver-structure.md)

 

 




