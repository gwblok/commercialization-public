---
title: Title
description: Title
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3073c3eb-b563-4887-b92e-d452669f434b
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Title


The `Title` setting specifies customized text to display next to the **Online Support** icon in the **Additional Information** page in the **Troubleshooting** Control Panel.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Title_ID</em></p></td>
<td><p>Specifies the title of the <strong>Online Support</strong> icon.</p>
<p><em>TitleID</em> is represented as <em><xref href="dllname,-resourceID" data-throw-if-not-resolved="False" data-raw-source="@dllname,-resourceID"></xref></em>, where <em>dllname</em> must include a full path to the resource DLL.</p>
<p>For information about creating localized versions of a DLL for each setting, see the MSDN topic: <a href="http://go.microsoft.com/fwlink/?LinkId=140252" data-raw-source="[Using the MUI with Applications](http://go.microsoft.com/fwlink/?LinkId=140252)">Using the MUI with Applications</a>.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


offlineServicing

generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-DiagCpl](microsoft-windows-diagcpl.md) | **Title**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-DiagCpl](microsoft-windows-diagcpl.md).

## XML Example


The following XML output shows how to configure the **Online Support** icon to point to the Fabrikam Troubleshooting application.

```
  <Title>@%SystemRoot%\System32\DiagCpl.dll,-82</Title>
  <Description>@%SystemRoot%\System32\DiagCpl.dll,-83</Description>
  <Icon>@%SystemRoot%\System32\imageres.dll,-179</Icon>
  <Link>http://www.fabrikam.com/support</Link>
```

## Related topics


[Microsoft-Windows-DiagCpl](microsoft-windows-diagcpl.md)

 

 







