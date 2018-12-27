---
title: Icon
description: Icon
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d3dbfb7b-d82e-4ee9-90ae-c8c2893ee5f5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Icon


The `Icon` setting specifies the path to a file that contains the icon graphic for the **Online Support** icon in the **Additional Information** page located in the **Troubleshooting** Control Panel.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>icon_ID</em></p></td>
<td><p>Specifies the icon graphic for the <strong>Online Support</strong> icon.</p>
<p><em>IconID</em> is represented as <em><xref href="dllname,-resourceID" data-throw-if-not-resolved="False" data-raw-source="@dllname,-resourceID"></xref></em>, where <em>dllname</em> must include a full path to the resource DLL.</p>
<p>For information about creating localized versions of a DLL for each setting, see the MSDN topic: <a href="http://go.microsoft.com/fwlink/?LinkId=140252" data-raw-source="[Using the MUI with Applications](http://go.microsoft.com/fwlink/?LinkId=140252)">Using the MUI with Applications</a>.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


offlineServicing

generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-DiagCpl](microsoft-windows-diagcpl.md) | **Icon**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-DiagCpl](microsoft-windows-diagcpl.md).

## XML Example


The following XML output shows how to configure the **Additional Information** icon to point to the Fabrikam Troubleshooting application.

```
  <Title>@%SystemRoot%\System32\DiagCpl.dll,-82
</Title>
  <Description>@%SystemRoot%\System32\DiagCpl.dll,-83</Description>
  <Icon>C@%SystemRoot%\System32\imageres.dll,-179</Icon>
  <Link>http://www.fabrikam.com/support</Link>
```

## Related topics


[Microsoft-Windows-DiagCpl](microsoft-windows-diagcpl.md)

 

 







