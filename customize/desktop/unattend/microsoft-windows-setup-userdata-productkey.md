---
title: ProductKey
description: ProductKey
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e2270219-f566-4116-bd76-f7342cf493d6
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# ProductKey

`ProductKey` contains settings that specify which edition of Windows to install. The product key that you purchase determines which edition you can install.

> [!Note]
> For more information about product keys, see the topic [Work with Product Keys and Activation](http://go.microsoft.com/fwlink/p/?linkid=208192) in the Windows Assessment and Deployment Kit (Windows ADK).

## Comparison of Product Key Settings

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="microsoft-windows-setup-userdata-productkey-key.md" data-raw-source="[Microsoft-Windows-Setup\UserData\ProductKey\Key](microsoft-windows-setup-userdata-productkey-key.md)">Microsoft-Windows-Setup\UserData\ProductKey\Key</a></p></td>
<td><p>Specifies the Windows image to install during Windows Setup.</p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-shell-setup-productkey.md" data-raw-source="[Microsoft-Windows-Shell-Setup\ProductKey](microsoft-windows-shell-setup-productkey.md)">Microsoft-Windows-Shell-Setup\ProductKey</a></p></td>
<td><p>Specifies a product key to activate Windows with. This setting can be used with microsoft-windows-setup-\UserData\ProductKey\Key, and the two product keys can be different.</p>
<p>If you are using a Volume License Multiple Activation Key (MAK), you must specify the MAK by using this setting.</p></td>
</tr>
</tbody>
</table>

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Key](microsoft-windows-setup-userdata-productkey-key.md) | Specifies the product key. |
| [WillShowUI](microsoft-windows-setup-userdata-productkey-willshowui.md) | Specifies the circumstances in which the user interface (UI) for the product key will be displayed. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | [UserData](microsoft-windows-setup-userdata.md) | **ProductKey**

## Applies To

For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output shows how to set user data.

```XML
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
