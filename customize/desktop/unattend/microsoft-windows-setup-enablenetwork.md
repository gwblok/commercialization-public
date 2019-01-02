---
title: EnableNetwork
description: EnableNetwork
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ecffdab9-99bd-4e85-9bde-6505a341c7ec
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# EnableNetwork


`EnableNetwork` specifies whether network connection is enabled. This setting applies only to Windows Preinstallation Environment (Windows PE).

If you set `EnableNetwork` to **false**, network initialization is skipped, and any network settings are ignored.

In OEM, independent software vendor, or other customized Windows PE scenarios, the default value for `EnableNetwork` is **true**. In Windows Setup scenarios, the default value is **false**.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that network connection is enabled.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that network connection is not enabled.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | **EnableNetwork**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to disable network connection.

```
<EnableNetwork>false</EnableNetwork>
```

## Related topics


[microsoft-windows-setup-](microsoft-windows-setup.md)

 

 







