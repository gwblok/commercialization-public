---
title: ProviderName
description: ProviderName
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: baf6dfbf-a34e-496f-aa51-6caa45e01848
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ProviderName


`ProviderName` specifies the name of the backup provider of an online backup service in the Windows Server Backup menus.

Before an online backup service is installed, Windows describes a recommended service. The provider name is part of the description.

After an online backup service is installed, this provider name continues to appear in the Windows Server Backup menus.

The provider name is added to the resource DLL file that the [ResourceDll](microsoft-windows-blb-wsb-online-main-resourcedll.md) setting specifies. The icon may be localized for different regions. For information about how to create localized versions for these settings, see [Using the MUI with Applications](http://go.microsoft.com/fwlink/?LinkId=140252).

The provider name in the resource DLL file must be a text string. For example, the provider name may resemble the following:

`Fabrikam Online Backup`

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>ResourceID</em></p></td>
<td><p>Specifies the resource ID from the resource DLL file for the provider name.</p>
<p><em>ResourceID</em> is an integer.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-BLB-WSB-Online-Main](microsoft-windows-blb-wsb-online-main.md) | **ProviderName**

## Applies To


For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-BLB-WSB-Online-Main](microsoft-windows-blb-wsb-online-main.md).

## XML Example


The following XML output shows how to describe a recommended online backup service. This includes provider information, descriptions, links, and an icon.

```
<EnableOnlineBackup>true</EnableOnlineBackup>
<ResourceDll>%ProgramFiles%\Microsoft Shared\Resource.dll</ResourceDll>
<ProviderName>100</ProviderName>
<Icon>101</Icon>
<Link1>200</Link1>
<Link1Text>201<Link1Text>
<DescriptionText1>202</DescriptionText1>
<Link2>300</Link2>
<Link2Text>301<Link2Text>
<DescriptionText2>302</DescriptionText2>
```

## Related topics


[Microsoft-Windows-BLB-WSB-Online-Main](microsoft-windows-blb-wsb-online-main.md)

[ResourceDll](microsoft-windows-blb-wsb-online-main-resourcedll.md)

 

 







