---
title: ResourceDll
description: ResourceDll
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 136a4f0a-4058-4a26-afba-bae38063f781
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ResourceDll


`ResourceDll` specifies the resource DLL file that is used for multiple settings that describe an online backup service in the Windows Server Backup menus. These settings include Microsoft-Windows-BLB-WSB-Online-Main\\[DescriptionText1](microsoft-windows-blb-wsb-online-main-descriptiontext1.md), [DescriptionText2](microsoft-windows-blb-wsb-online-main-descriptiontext2.md), [Icon](microsoft-windows-blb-wsb-online-main-icon.md), [Link1](microsoft-windows-blb-wsb-online-main-link1.md), [Link1Text](microsoft-windows-blb-wsb-online-main-link1text.md), [Link2](microsoft-windows-blb-wsb-online-main-link2.md), [Link2Text](microsoft-windows-blb-wsb-online-main-link2text.md), and [ProviderName](microsoft-windows-blb-wsb-online-main-providername.md).

For information about how to create localized versions for these settings, see the topic [Using the MUI with Applications](http://go.microsoft.com/fwlink/?LinkId=140252).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path</em></p></td>
<td><p>Specifies the path and file name of a resource DLL file.</p>
<p><em>Path</em> is a string that has a maximum length of 259 characters.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

oobeSystem

## Parent Hierarchy


[Microsoft-Windows-BLB-WSB-Online-Main](microsoft-windows-blb-wsb-online-main.md) | **ResourceDll**

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

[DescriptionText1](microsoft-windows-blb-wsb-online-main-descriptiontext1.md)

[DescriptionText2](microsoft-windows-blb-wsb-online-main-descriptiontext2.md)

[Icon](microsoft-windows-blb-wsb-online-main-icon.md)

[Link1](microsoft-windows-blb-wsb-online-main-link1.md)

[Link1Text](microsoft-windows-blb-wsb-online-main-link1text.md)

[Link2](microsoft-windows-blb-wsb-online-main-link2.md)

[Link2Text](microsoft-windows-blb-wsb-online-main-link2text.md)

[ProviderName](microsoft-windows-blb-wsb-online-main-providername.md)

 

 







