---
title: InternalAdapter
description: InternalAdapter
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d6054e2b-b4e5-4119-b3be-05fd6c0dab79
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# InternalAdapter


`InternalAdapter` specifies the internal adapter for Internet-connection sharing. This cannot be used as part of a network bridge.

This setting has no effect on Server Core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Internal_adapter_name</em></p></td>
<td><p>Specifies the internal adapter for Internet-connection sharing. <em>Internal_adapter_name</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


generalize

## Parent Hierarchy


[Microsoft-Windows-SharedAccess](microsoft-windows-sharedaccess.md) | **InternalAdapter**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-SharedAccess](microsoft-windows-sharedaccess.md).

## XML Example


The following XML output shows how to set Shared Access.

```
<EnableICS>true</EnableICS>
<ExternalAdapter>MyExternalAdapter</ExternalAdapter>
<InternalAdapter>MyInternalAdapter</InternalAdapter>
```

## Related topics


[Microsoft-Windows-SharedAccess](microsoft-windows-sharedaccess.md)

[Bridge](microsoft-windows-networkbridge-bridge.md)

 

 







