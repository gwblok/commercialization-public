---
title: DescriptionText2
description: DescriptionText2
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 50683aae-5c38-4469-b80c-045e723ff6bb
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DescriptionText2


`DescriptionText2` specifies the second of two lines of a description of an online backup service in the Windows Server Backup menus.

Before an online backup service is installed, Windows displays a description of a recommended online backup service. This text is part of the description.

This description text is added to the resource DLL file that the [ResourceDll](microsoft-windows-blb-wsb-online-main-resourcedll.md) setting specifies, and may be localized for different regions. For information about how to create localized versions for these settings, see [Using the MUI with Applications](http://go.microsoft.com/fwlink/p/?linkid=247425).

The description text in the resource DLL file must be a text string. For example, the description may resemble the following:

`The full version includes additional features, such as Recovery Feature 1 and Recovery Feature 2`.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>ResourceID</em></p></td>
<td><p>Specifies the resource ID from the resource DLL file for the second of two lines of the description of the online backup service.</p>
<p><em>ResourceID</em> is an integer.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-BLB-WSB-Online-Main](microsoft-windows-blb-wsb-online-main.md) | **DescriptionText2**

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

 

 







