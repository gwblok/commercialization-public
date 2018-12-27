---
title: Restart
description: Restart
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2bfabdf7-cd94-4fa8-a9e6-9bed0677db8d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Restart


`Restart` specifies whether to restart or to shut down the computer after the windowsPE configuration pass. This setting is specific to Windows PE scenarios. Once image-based installation begins, this setting is ignored.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Restart</strong></p></td>
<td><p>Specifies that the computer immediately restarts after the windowsPE configuration pass. End users cannot disable the restart. This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>Shutdown</strong></p></td>
<td><p>Specifies that the computer immediately shuts down after the windowsPE configuration pass. End users cannot disable the shutdown.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | **Restart**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to set the computer to shut down after the windowsPE configuration pass.

```
<Restart>Shutdown</Restart>
```

## Related topics


[microsoft-windows-setup-](microsoft-windows-setup.md)

 

 







