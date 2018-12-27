---
title: InitialOEMServiceProvider
description: InitialOEMServiceProvider
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4fa1609d-b29e-4ec6-82f2-364719941550
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# InitialOEMServiceProvider


`InitialOEMServiceProvider` specifies the initial service provider for Windows Media Player 12. The service provider specified is the initial active Online Store when the user first runs Windows Media Player and completes the Windows Media Player First-Use Experience Configuration Wizard. The value used for this setting is obtained from the Online Store provider.

## Value


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>InitialOEMServiceProviderID</em></p></td>
<td><p>Specifies the default service provider for Windows Media Player 12. <em>InitialOEMServiceProviderID</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-MediaPlayer-Core](microsoft-windows-mediaplayer-core.md) | **InitialOEMServiceProvider**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-MediaPlayer-Core](microsoft-windows-mediaplayer-core.md).

## XML Example


The following XML output shows how to configure the `InitialOEMServiceProvider` setting.

```
<InitialOEMServiceProvider>MyOEMServiceProviderID</InitialOEMServiceProvider>
```

## Related topics


[Microsoft-Windows-MediaPlayer-Core](microsoft-windows-mediaplayer-core.md)

 

 







