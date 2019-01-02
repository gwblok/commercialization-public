---
title: ItemKey
description: ItemKey
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d5f04b4e-950e-4dc8-a045-0acc1663377a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ItemKey


`ItemKey` contains a unique key for [Accelerator](microsoft-windows-ie-internetexplorer-accelerators-accelerator.md).

Accelerators are menu options in Internet Explorer that help to automate common browser-related tasks. In Internet Explorer, when you right-click selected text, Accelerators appear in the list of available options. For example, if you right-click a selected address, you can use an Accelerator to show a map of that address.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Key</em></p></td>
<td><p>Specifies a unique key for the <strong>AcceleratorsXML</strong>. <em>Key</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy
microsoft-windows-ie-internetexplorer.md) | [Accelerators](microsoft-windows-ie-internetexplorer-accelerators.md) | [Accelerator](microsoft-windows-ie-internetexplorer-accelerators-accelerator.md) | `ItemKey`

## Applies To


For a list of Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output specifies adding two Accelerators.

```
<Accelerators>
  <Accelerator wcm:action="add">
    <AcceleratorXML>C:\Fabrikam\Accelerator1.xml</AcceleratorXML>
    <ItemKey>Accelerator1</ItemKey> 
    <IsDefault>true</IsDefault> 
  </Accelerator>
  <Accelerator wcm:action="add">
    <AcceleratorXML>C:\Fabrikam\Accelerator2.xml</AcceleratorXML> 
    <ItemKey>Accelerator2</ItemKey> 
  </Accelerator>
</Accelerators>
```

## Related topics


[Accelerator](microsoft-windows-ie-internetexplorer-accelerators-accelerator.md)

 

 







