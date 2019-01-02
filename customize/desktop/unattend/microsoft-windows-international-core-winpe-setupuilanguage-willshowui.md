---
title: WillShowUI
description: WillShowUI
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 89998616-b3b4-4741-b114-2f41325c055d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# WillShowUI


**Important**  
This setting is deprecated and should not be used. This information is included for reference only.

 

## Value


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Always</strong></p></td>
<td><p>Specifies to always show the Windows Setup user interface (UI).</p></td>
</tr>
<tr class="even">
<td><p><strong>onError</strong></p></td>
<td><p>Specifies that Windows Setup displays the UI only when an error with the international settings occurs. This is the default value.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Never</strong></p></td>
<td><p>Specifies never to display the Windows Setup UI.</p></td>
</tr>
</tbody>
</table>

 

## Parent Hierarchy


[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md) | [SetupUILanguage](microsoft-windows-international-core-winpe-setupuilanguage.md) | **WillShowUI**

## Valid Configuration Passes


windowsPE

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md).

## XML Example


The following XML output shows how to configure the Windows Setup UI language to display French (France).

```
   <SetupUILanguage>
       <UILanguage>fr-FR</UILanguage>
   </SetupUILanguage>
```

## Related topics


[microsoft-windows-international-core-winpe--](microsoft-windows-international-core-winpe.md)

[SetupUILanguage](microsoft-windows-international-core-winpe-setupuilanguage.md)

[Microsoft-Windows-International-Core](microsoft-windows-international-core.md)

 

 







