---
title: Key
description: Key
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9b802811-1348-4616-add9-47156c1c5961
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Key


`Key` specifies the 25-character product key that determines which edition of Windows to install. Use the correct product key for the edition of Windows that you are installing. For more information about using product keys in answer files, see the [Work with Product Keys and Activation](http://go.microsoft.com/fwlink/?LinkId=206615) topic in the Windows Assessment and Deployment Kit (Windows ADK) Technical Reference.

The product key that you use to activate the installation must match the number on the Certificate of Authenticity (COA) sticker that accompanies the retail product or that is physically attached to the computer case by the original equipment manufacturer (OEM).

Standard licensing agreements specify that you can use a product key only to activate one installation of Windows on one computer. Windows Product Activation enforces this requirement.

## Comparison of Product Key Settings


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>microsoft-windows-setup-\UserData\ProductKey&lt;code&gt;Key</code></p></td>
<td><p>Specifies the Windows image to install during Windows Setup.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-Shell-Setup<a href="microsoft-windows-setup-userdata-productkey.md" data-raw-source="[ProductKey](microsoft-windows-setup-userdata-productkey.md)">ProductKey</a></p></td>
<td><p>Specifies a product key to activate Windows. This setting can be used with microsoft-windows-setup-\UserData\ProductKey\Key, and the two product keys can be different.</p>
<p>If you are using a Volume-License Multiple-Activation Key (MAK), it must be specified using this setting.</p></td>
</tr>
</tbody>
</table>

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>product_key</em></p></td>
<td><p>Specifies the product key to apply to an installation of Windows.</p>
<p>Product keys are 25 characters in the following format:</p>
<p><em>xxxxx-xxxxx-xxxxx-xxxxx-xxxxx</em></p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [UserData](microsoft-windows-setup-userdata.md) | [ProductKey](microsoft-windows-setup-userdata-productkey.md) | **Key**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to set user data.

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


[ProductKey](microsoft-windows-setup-userdata-productkey.md)

 

 







