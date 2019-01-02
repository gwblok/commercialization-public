---
title: AcceptEula
description: AcceptEula
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9818a53a-be85-416f-ba6d-8fd8841d770f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# AcceptEula


`AcceptEula` specifies whether to automatically accept the Microsoft Software License Terms.

**Note**  
This setting is required for all unattended installations. To prevent the Windows Setup user interface (UI) from displaying, you must configure this setting. For a complete list of required settings, see the [How to Automate Windows Setup](http://go.microsoft.com/fwlink/?LinkId=206673) topic in the Windows Assessment and Deployment Kit (Windows ADK) Technical Reference.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the license terms are automatically accepted without being displayed to the end user.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Prompts the end user to accept the license terms before proceeding with Windows Setup. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
The value for `AcceptEula` is ignored during upgrades.

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [UserData](microsoft-windows-setup-userdata.md) | **AcceptEula**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following sample XML output shows how to set user data.

```
<UserData>
   <AcceptEula>true</AcceptEula>
   <FullName>EndUserName</FullName>
   <Organization>Fabrikam</Organization>
   <ProductKey>
      <Key>12345-12345-12345-12345-12345</Key>
      <WillShowUI>Never</WillShowUI>
   </ProductKey>
</UserData>
```

## Related topics


[UserData](microsoft-windows-setup-userdata.md)

 

 







