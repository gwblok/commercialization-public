---
title: ShowPowerButtonOnStartScreen
description: ShowPowerButtonOnStartScreen
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7b20e8e2-56f1-4f72-a34a-32d32a4a41e9
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ShowPowerButtonOnStartScreen


`ShowPowerButtonOnStartScreen` specifies that the **Power Options** button is visible on the Start screen.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the <strong>Power Options</strong> button is visible on the Start screen.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the <strong>Power Options</strong> button is not visible on the Start screen.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
The default value of **ShowWindowsStoreAppsOnTaskbar** depends on the selected power platform role.

 

## Valid Configuration Passes


auditUser

oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **ShowPowerButtonOnStartScreen**

## Applies To


For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to show the Power Options button on the Start Screen.

```
<ShowPowerButtonOnStartScreen>true</ShowPowerButtonOnStartScreen>
```

## Related topics


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)

 

 







