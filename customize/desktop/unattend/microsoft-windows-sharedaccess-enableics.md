---
title: EnableICS
description: EnableICS
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3e26f9dd-a079-4b0a-aece-a1501dd54c35
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# EnableICS


`EnableICS` specifies whether Internet-connection sharing is enabled.

This setting has no effect on Server Core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Enables Internet-connection sharing.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Disables Internet-connection sharing. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

## Parent Hierarchy


[Microsoft-Windows-SharedAccess](microsoft-windows-sharedaccess.md) | **EnableICS**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-SharedAccess](microsoft-windows-sharedaccess.md).

## XML Example


The following XML output shows how to set Shared Access.

```
<EnableICS>true</EnableICS>
<InternalIsBridge>true</InternalIsBridge>
<ExternalAdapter>MyExternalAdapter</ExternalAdapter>
```

## Related topics


[Microsoft-Windows-SharedAccess](microsoft-windows-sharedaccess.md)

[Microsoft-Windows-NetworkBridge](microsoft-windows-networkbridge.md)

 

 







