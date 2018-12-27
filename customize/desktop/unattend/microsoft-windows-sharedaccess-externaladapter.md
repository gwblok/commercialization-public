---
title: ExternalAdapter
description: ExternalAdapter
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2b8745d1-06e6-40a5-82be-8989feb1132f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ExternalAdapter


`ExternalAdapter` specifies the external adapter for Internet-connection sharing. This cannot be used as part of a network bridge.

This setting has no effect on Server Core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>External_adapter_name</em></p></td>
<td><p>Specifies the external adapter. <em>External_adapter_name</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


generalize

## Parent Hierarchy


[Microsoft-Windows-SharedAccess](microsoft-windows-sharedaccess.md) | **ExternalAdapter**

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

[Bridge](microsoft-windows-networkbridge-bridge.md)

 

 







