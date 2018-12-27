---
title: IsDefault
description: IsDefault
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8c983a8e-fa5b-4a7d-b9e9-66ebb59e1196
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# IsDefault


`IsDefault` specifies the default Internet Explorer Accelerator.

Accelerators are menu options in Internet Explorer that help to automate common browser-related tasks. In Internet Explorer, when you right-click selected text, Accelerators appear in the list of available options. For example, if you select an address, you can use an Accelerator to show a map of that address.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>true</p></td>
<td><p>Specifies the Accelerator as default in the list of Accelerators.</p></td>
</tr>
<tr class="even">
<td><p>false</p></td>
<td><p>Does not specify the Accelerator as default in the list of Accelerators.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [Accelerators](microsoft-windows-ie-internetexplorer-accelerators.md) | [Accelerator](microsoft-windows-ie-internetexplorer-accelerators-accelerator.md) | `IsDefault`

## Applies To


For a list of Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output specifies adding two Accelerators, and specifies the first Accelerator as the default.

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

 

 







