---
title: ProductKey
description: ProductKey
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9c0b8b7c-382a-48d9-ad3c-4d23d0dae2db
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ProductKey


`ProductKey` specifies the product key to use for Windows activation.

**Important**  
Entering an invalid product key in the answer file will cause Windows Setup to fail.

 

If you are using a Volume License Multiple Activation Key (MAK), you must specify it in the `ProductKey` setting. If you preinstall Windows under a volume license agreement, consult your specific license agreement to determine the number of installations permitted per product key. For more information about product keys, see [Work with Product Keys and Activation](http://go.microsoft.com/fwlink/?LinkId=206615) in the Windows Assessment and Deployment Kit (Windows ADK) Technical Reference.

## Comparison of Product Key Settings


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>microsoft-windows-setup-\UserData\ProductKey<a href="microsoft-windows-setup-userdata-productkey-key.md" data-raw-source="[Key](microsoft-windows-setup-userdata-productkey-key.md)">Key</a></p></td>
<td><p>Specifies the Windows image to install during Windows Setup.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft-Windows-Shell-Setup&lt;code&gt;ProductKey</code></p></td>
<td><p>Specifies a Product Key to activate Windows. This setting can be used with microsoft-windows-setup-\UserData\ProductKey&lt;code&gt;Key</code>. The two product keys can be different.</p></td>
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
<td><p><em>Product_key</em></p></td>
<td><p>Specifies the key used to install and to activate Windows. <em>Product_key</em> is a 29-character string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **ProductKey**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to set the product key.

```
<ProductKey>AAAAA-BBBBB-CCCCC-DDDDD-EEEEE</ProductKey>
```

## Related topics


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)

 

 







