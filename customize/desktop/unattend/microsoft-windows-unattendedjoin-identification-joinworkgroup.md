---
title: JoinWorkgroup
description: JoinWorkgroup
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7853b2fd-7954-46e0-bd05-f0c36e4efa52
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# JoinWorkgroup


`JoinWorkgroup` specifies the name of the workgroup to assign to a computer. If this value is set, [JoinDomain](microsoft-windows-unattendedjoin-identification-joindomain.md) cannot be set.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>JoinWorkgroup</em></p></td>
<td><p>Specifies the name of the workgroup to apply to a computer during Windows Setup. <em>JoinWorkgroup</em> is a string and must be a valid NetBIOS name.</p>
<p>You can specify either a domain to join or a workgroup to assign, by using <a href="microsoft-windows-unattendedjoin-identification-joindomain.md" data-raw-source="[JoinDomain](microsoft-windows-unattendedjoin-identification-joindomain.md)">JoinDomain</a> or <em>JoinWorkgroup</em> settings, respectively. However, only one of these settings can be present in an answer file. If both are present in an answer file, the value for <em>JoinDomain</em> is used, and <em>JoinWorkgroup</em> is ignored.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | **JoinWorkgroup**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example


The following XML output shows how to set the identification settings.

```
<Identification>
   <JoinWorkgroup>MyWorkgroup</JoinWorkgroup>
</Identification>
```

## Related topics


[Identification](microsoft-windows-unattendedjoin-identification.md)

 

 







