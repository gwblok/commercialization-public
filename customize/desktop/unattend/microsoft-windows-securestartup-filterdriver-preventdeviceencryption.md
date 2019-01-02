---
title: PreventDeviceEncryption
description: PreventDeviceEncryption
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 263bc799-4ea2-49db-86f3-547d20fc1618
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PreventDeviceEncryption


`PreventDeviceEncryption` prevents encrypting the operating system drive and any fixed data drive using Windows BitLocker Drive Encryption. Device encryption is a feature available on Windows 8.1 PCs that supports InstantGo. When a user boots the PC for the first time and goes through the out-of-the-box experience, device encryption, on initialization, will automatically encrypt the operating system drive and any fixed data drive using BitLocker.

Use this setting to prevent device encryption from automatically encrypting the operating system drive and any fixed data drive using BitLocker.

**Note**  
These settings only apply to Windows 8.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>false</strong></p></td>
<td><p>Automatically encrypt the operating system drive and any fixed data drive using BitLocker.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>true</strong></p></td>
<td><p>Do not automatically encrypt the operating system and any fixed data drive using BitLocker.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


offlineServicing

specialize

auditSystem

oobeSystem

## Parent Hierarchy


[microsoft-windows-securestartup-filterdriver-](microsoft-windows-securestartup-filterdriver.md) | **PreventDeviceEncryption**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-securestartup-filterdriver-](microsoft-windows-securestartup-filterdriver.md).

## XML Example


The following example configures Windows 8.1 to not automatically encrypt the operating system drive and any fixed data drive using BitLocker when the PC first boots.

```
<component name="microsoft-windows-securestartup-filterdriver-" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS">
      <PreventDeviceEncryption>true</PreventDeviceEncryption>
</component
```

## Related topics


[microsoft-windows-securestartup-filterdriver-](microsoft-windows-securestartup-filterdriver.md)

 

 







