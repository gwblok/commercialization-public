---
title: Link
description: Link
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8d5c2f06-d09f-4e14-8a6c-2a5bfe10e888
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Link


The `Link` setting specifies a GUID of the **Online Support** icon in the **Additional Information** page located in the **Troubleshooting** Control Panel.

For information about finding the GUID for your icon, see the MSDN topic: [NOTIFYICONDATA Structure](http://go.microsoft.com/fwlink/?LinkId=120340).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>GUID</em> or <em>URL</em></p></td>
<td><p>Specifies either a <em>GUID</em> of an application or a <em>URL</em> to a website which is called when the user selects the <strong>Online Support</strong> icon.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


offlineServicing

generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-DiagCpl](microsoft-windows-diagcpl.md) | **Link**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-DiagCpl](microsoft-windows-diagcpl.md).

## XML Example


The following XML output shows how to configure the **Additional Information** icon to point to the Fabrikam Troubleshooting application by using a GUID to specify the application location.

```
  <Title>@%SystemRoot%\System32\DiagCpl.dll,-82</Title>
  <Description>@%SystemRoot%\System32\DiagCpl.dll,-83</Description>
  <Icon>@%SystemRoot%\System32\imageres.dll,-179</Icon>
  <Link>{abcde-01234-fabc01234def-39393}</Link>
```

The following XML output shows how to configure the **Additional Information** icon to point to the Fabrikam Support website by using a URL.

```
  <Title>@%SystemRoot%\System32\DiagCpl.dll,-82</Title>
  <Description>@%SystemRoot%\System32\DiagCpl.dll,-83</Description>
  <Icon>@%SystemRoot%\System32\imageres.dll,-179</Icon>
  <Link>http://www.fabrikam.com/support</Link>
```

## Related topics


[Microsoft-Windows-DiagCpl](microsoft-windows-diagcpl.md)

 

 







