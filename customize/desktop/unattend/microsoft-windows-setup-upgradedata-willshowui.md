---
title: WillShowUI
description: WillShowUI
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 078ba908-2684-4ffa-b3c9-8a2700c62989
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# WillShowUI


`WillShowUI` specifies in what circumstances the user interface (UI) is displayed for [UpgradeData](microsoft-windows-setup-upgradedata.md).

**Note**  
Windows Setup does not support using any other unattended Setup settings during upgrades. When you upgrade from an earlier version of Windows, you must create an answer file that includes only the Windows-Setup\\UpgradeData settings. Then, you must use either the Windows product DVD or the System Preparation (sysprep) tool to upgrade Windows.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Always</strong></p></td>
<td><p>Specifies that the UI is always displayed for this item.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnError</strong></p></td>
<td><p>Specifies that the UI is displayed for this item when an error occurs. This is the default value.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Never</strong></p></td>
<td><p>Specifies that the UI is never displayed for this item.</p>
<p><code>WillShowUI</code> only prevents Windows Setup UI pages from being displayed. If a critical error occurs, an error message might be displayed. To avoid displaying the error message, you can use the ErrorHandler.cmd file to automatically run a script to handle the error. For more information about ErrorHandler.cmd, see <a href="https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/add-a-custom-script-to-windows-setup" data-raw-source="[Add a custom script to Windows Setup](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/add-a-custom-script-to-windows-setup)">Add a custom script to Windows Setup</a>.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [UpgradeData](microsoft-windows-setup-upgradedata.md) | **WillShowUI**

## Applies To


For the list of the Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## <a href="" id="xmlexample"></a>XML Example


The following XML output shows how to set an upgrade installation to run in guaranteed quiet mode.

```
<UpgradeData>
   <Upgrade>true</Upgrade>
   <WillShowUI>Never</WillShowUI>
</UpgradeData>
```

## Related topics


[UpgradeData](microsoft-windows-setup-upgradedata.md)

 

 







