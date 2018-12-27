---
title: BluetoothTaskbarIconEnabled
description: BluetoothTaskbarIconEnabled
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f0669dde-144d-4628-a8e9-0fc5c108a0ec
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# BluetoothTaskbarIconEnabled


`BluetoothTaskbarIconEnabled` specifies whether the Bluetooth taskbar icon should appear in the taskbar.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the Bluetooth icon is displayed in the taskbar.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the Bluetooth icon is not displayed in the taskbar.</p></td>
</tr>
</tbody>
</table>

 

By default, Windows displays the Bluetooth icon when the system has a Bluetooth module or adapter. Otherwise, the icon is not displayed.

## Valid Configuration Passes


auditUser

generalize

offlineServicing

oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **BluetoothTaskbarIconEnabled**

## Applies To


This setting has no effect on Server Core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012.

For a list of other supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md). This setting is not configured in a Nano Server image.

## XML Example


The following XML output shows how to enable the Bluetooth taskbar.

```
<BluetoothTaskbarIconEnabled>true</BluetoothTaskbarIconEnabled>
```

## Related topics


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)

 

 







