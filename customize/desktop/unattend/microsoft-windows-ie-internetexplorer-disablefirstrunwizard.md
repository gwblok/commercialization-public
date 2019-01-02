---
title: DisableFirstRunWizard
description: DisableFirstRunWizard
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4858dde1-88d3-4d1f-9670-91ba85e3bf7f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DisableFirstRunWizard


`DisableFirstRunWizard` specifies whether to skip the First Run Wizard when the user runs Windows Internet Explorer for the first time.

The Internet Explorer First Run Wizard helps users complete the browser-installation process by prompting them to define the default search provider, the phishing filter settings, and so on.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Skips the First Run Wizard when Internet Explorer runs for the first time. When the user opens the browser, the default values for the installation process are selected.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Starts the First Run Wizard when Internet Explorer runs for the first time. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **DisableFirstRunWizard**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to skip the First Run Wizard when Internet Explorer runs for the first time.

```
<DisableFirstRunWizard>true</DisableFirstRunWizard>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







