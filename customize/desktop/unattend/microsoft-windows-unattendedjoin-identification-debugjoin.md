---
title: DebugJoin
description: DebugJoin
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3679b105-90d2-4a13-9cbd-891fec407792
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DebugJoin


`DebugJoin` specifies a trigger to run the debugging routine if setup encounters an error code. This setting enables you to debug Windows Setup failures. Additionally, if a specific error code is used with [DebugJoinOnlyOnThisError](microsoft-windows-unattendedjoin-identification-debugjoinonlyonthiserror.md), `DebugJoin` will apply only for failures with the specified error code. For more information, see DebugJoinOnlyOnThisError.

**Important**  
This is an advanced setting designed to be used by product development and Microsoft Product Support Services. Leave this setting unmodified when you configure the unattended answer file.

If `DebugJoin` is specified, a trace file is generated during the domain join process (%WINDIR%\\Panther\\UnattendGC\\UnattendedJoinDCLocator.etl). This trace file can be useful for diagnosing network connectivity issues during setup that might prevent domain join from succeeding.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Triggers a debugging routine if the domain join operation fails for any reason. If the computer has a kernel debugger attached, it immediately breaks into the debugger after the failed domain join operation. This setting is primarily designed for internal debugging.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Adds the computer to the domain without performing debugging tasks. This is the default value if <code>DebugJoin</code> is not specified.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | **DebugJoin**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example


The following XML output shows how to set debug joins.

```
<DebugJoin>true</DebugJoin>
```

## Related topics


[Identification](microsoft-windows-unattendedjoin-identification.md)

 

 







