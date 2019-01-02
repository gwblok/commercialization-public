---
title: EnableOnlineBackup
description: EnableOnlineBackup
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f842d4ad-6730-4eff-8e48-88d70eb9da82
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# EnableOnlineBackup


`EnableOnlineBackup` specifies whether a recommended online backup service appears in the Windows Server Backup menus.

By default, the Windows Server Backup menus show a recommended online backup service. By default, this service is Windows Azure Online Backup. You can select another default cloud backup service by setting the other settings in the [Microsoft-Windows-BLB-WSB-Online-Main](microsoft-windows-blb-wsb-online-main.md) component.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that a recommended online backup service appears in the Windows Server Backup menus.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that no recommendations for online backup services appear in the Windows Server Backup menus.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-BLB-WSB-Online-Main](microsoft-windows-blb-wsb-online-main.md) | **EnableOnlineBackup**

## Applies To


For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-BLB-WSB-Online-Main](microsoft-windows-blb-wsb-online-main.md).

## XML Example


The following XML output shows how to specify that no recommendations for online backup services appear in the Windows Server Backup menus.

```
<EnableOnlineBackup>false</EnableOnlineBackup>
```

## Related topics


[Microsoft-Windows-BLB-WSB-Online-Main](microsoft-windows-blb-wsb-online-main.md)

 

 







