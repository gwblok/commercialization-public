---
title: WillShowUI
description: WillShowUI
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7116ee10-76a2-4dff-aaa5-127a7a0fb9b4
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# WillShowUI


`WillShowUI` specifies in what circumstances to display the user interface (UI) when applying a product key specified by [ProductKey](microsoft-windows-setup-userdata-productkey.md).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Always</strong></p></td>
<td><p>Specifies that the UI is always displayed.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnError</strong></p></td>
<td><p>Specifies that the UI is displayed if an error occurs, even for catastrophic, non-recoverable errors. This is the default value.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Never</strong></p></td>
<td><p>Specifies that the UI is never displayed.</p>
<p><code>WillShowUI</code> only prevents Windows Setup UI pages from being displayed. If a critical error occurs, an error message might be displayed. To avoid displaying the error message, you can use the ErrorHandler.cmd file to automatically run a script to handle the error. For more information about ErrorHandler.cmd, see <a href="https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/add-a-custom-script-to-windows-setup" data-raw-source="[Add a custom script to Windows Setup](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/add-a-custom-script-to-windows-setup)">Add a custom script to Windows Setup</a>.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [UserData](microsoft-windows-setup-userdata.md) | [ProductKey](microsoft-windows-setup-userdata-productkey.md) | **WillShowUI**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

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

 

 







