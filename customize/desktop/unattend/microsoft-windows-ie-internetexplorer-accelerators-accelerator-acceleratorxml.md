---
title: AcceleratorXML
description: AcceleratorXML
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 441686c6-5135-40e6-8238-59f149890d87
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# AcceleratorXML


`AcceleratorXML` specifies the Uniform Resource Locator (URL) for an Internet Explorer Accelerator.

Accelerators are menu options in Internet Explorer that help to automate common browser-related tasks. In Internet Explorer, when you right-click selected text, Accelerators appear in the list of available options. For example, if you select an address, you can use an Accelerator to show a map of that address.

To configure an accelerator, add an AcceleratorXML file to the local computer, and then reference it by using this setting. For more information about configuring accelerators, see [this MSDN website](http://go.microsoft.com/fwlink/?LinkId=130617).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Path</p></td>
<td><p>Specifies a file location of an Accelerator XML file. <em>Path</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | [Accelerators](microsoft-windows-ie-internetexplorer-accelerators.md) | [Accelerator](microsoft-windows-ie-internetexplorer-accelerators-accelerator.md) | `AcceleratorXML`

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

 

 







