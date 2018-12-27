---
title: TimeoutPeriodInMinutes
description: TimeoutPeriodInMinutes
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ef1c71ca-cc4b-4ec9-b8b4-e946f0ff4005
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# TimeoutPeriodInMinutes


`TimeoutPeriodInMinutes` specifies the number of minutes that Windows will wait while attempting to join the computer to the domain before timing out.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Number of minutes</em></p></td>
<td><p>Specifies the number of minutes that Windows will wait before timing out when Windows tries to join a domain. <em>Number of minutes</em> must be between 5 and 60.</p></td>
</tr>
</tbody>
</table>

 

If no value is entered, or if an invalid value is entered, Windows will use 15 minutes as the default value.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | **TimeoutPeriodInMinutes**

## Applies To


Windows 8 and Windows Server 2012 only.

For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example


The following XML output shows how to set the default timeout period to 5 minutes.

```
<TimeoutPeriodInMinutes>5</TimeoutPeriodInMinutes>
```

## Related topics


[Identification](microsoft-windows-unattendedjoin-identification.md)

 

 







