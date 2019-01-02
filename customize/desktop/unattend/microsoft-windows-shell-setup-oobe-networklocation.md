---
title: NetworkLocation
description: NetworkLocation
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b77876d1-2112-490e-8b9b-6aca37d8b2d1
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# NetworkLocation


**Important**  
This setting has been deprecated in Windows 10. The information about this deprecated setting is provided for reference only.

 

`NetworkLocation` specifies the location of the network if the computer is connected to a network when a user first logs on.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Home</strong></p></td>
<td><p>Specifies a private home network.</p></td>
</tr>
<tr class="even">
<td><p><strong>Work</strong></p></td>
<td><p>Specifies a private office network.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Other</strong></p></td>
<td><p>Specifies neither a home or work network. Network discovery is disabled by default on this network type.</p></td>
</tr>
</tbody>
</table>

 

There is no default value. If a value is not set, and a network is detected, then the **Computer's Current Location** page opens during the Out of Box Experience (OOBE).

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OOBE](microsoft-windows-shell-setup-oobe.md) | **NetworkLocation**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML example shows how to set the network location to a private office network.

```
<OOBE>
   <NetworkLocation>Work</NetworkLocation>
</OOBE>
```

## Related topics


[OOBE](microsoft-windows-shell-setup-oobe.md)
[Automate OOBE](https://docs.microsoft.com/windows-hardware/customize/desktop/automate-oobe)
