---
title: DismLogLevel Enumeration
description: DismLogLevel Enumeration
ms.assetid: c0344b29-fe86-400a-a2d8-95d582ccef5a

ms.date: 10/25/2017
ms.topic: article


topic_type: 
- apiref
api_name: 
- DismLogLevel
api_location: 
- DismAPI.dll
api_type: 
- DllExport
---

# DismLogLevel Enumeration


Specifies the kind of information that is reported in the log file.

## <span id="Syntax"></span><span id="syntax"></span><span id="SYNTAX"></span>Syntax


``` syntax
enum DismLogLevel
{
    DismLogErrors = 0,
    DismLogErrorsWarnings = 1,
    DismLogErrorsWarningsInfo = 2
};
```

## <span id="Constants"></span><span id="constants"></span><span id="CONSTANTS"></span>Constants


<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Constant</th>
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>DismLogErrors</em></p></td>
<td><p>0</p></td>
<td><p>Log file only contains errors.</p></td>
</tr>
<tr class="even">
<td><p><em>DismLogErrorsWarnings</em></p></td>
<td><p>1</p></td>
<td><p>Log file contains errors and warnings.</p></td>
</tr>
<tr class="odd">
<td><p><em>DismLogErrorsWarningsInfo</em></p></td>
<td><p>2</p></td>
<td><p>Log file contains errors, warnings, and additional information.</p></td>
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
<td><p>Supported host platforms:</p></td>
<td><p>DISM API can be used on any operating system supported by the Windows® Assessment and Deployment Kit (Windows ADK). For more information, see the <a href="http://go.microsoft.com/fwlink/?LinkId=206587" data-raw-source="[Windows ADK Technical Reference](http://go.microsoft.com/fwlink/?LinkId=206587)">Windows ADK Technical Reference</a>.</p></td>
</tr>
<tr class="even">
<td><p>Supported image platforms:</p></td>
<td><p>Windows® 7, Windows Server 2008 R2, Windows PE 3.0, Windows 8, Windows Server® 2012, Windows Preinstallation Environment (Windows PE) 4.0</p></td>
</tr>
</tbody>
</table>

 

## <span id="related_topics"></span>Related topics


[DismInitialize Function](disminitialize-function.md)

 

 




