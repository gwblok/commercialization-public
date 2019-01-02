---
title: DebugJoinOnlyOnThisError
description: DebugJoinOnlyOnThisError
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 931796e5-7baa-4d02-889f-e0d6b7e74ca5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DebugJoinOnlyOnThisError


`DebugJoinOnlyOnThisError` specifies a particular error code that causes `DebugJoin` to trigger if encountered during Windows Setup.

This setting modifies the behavior of [DebugJoin](microsoft-windows-unattendedjoin-identification-debugjoin.md). If specified, this setting causes the DebugJoin behavior only when the domain join operation fails with the error specified by this setting.

`DebugJoinOnlyOnThisError` only functions if [DebugJoin](microsoft-windows-unattendedjoin-identification-debugjoin.md) is set to **true**.

**Important**  
This is an advanced setting designed to be used by product development and Microsoft Product Support Services. Leave this setting unmodified when you configure the unattended answer file.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Error_code</em></p></td>
<td><p>Specifies an error code. The value is the decimal error code to filter. <em>Error_code</em> is a string. The default value is <strong>0</strong>, meaning any error triggers the debug routine.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | **DebugJoinOnlyOnThisError**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example


The following XML output shows how to set debug joins.

```
<DebugJoin>true</DebugJoin>
<DebugJoinOnlyOnThisError>1355</DebugJoinOnlyOnThisError>
```

## Related topics


[Identification](microsoft-windows-unattendedjoin-identification.md)

 

 







