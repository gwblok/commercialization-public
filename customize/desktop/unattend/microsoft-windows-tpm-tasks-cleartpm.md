---
title: Microsoft-Windows-TPM-Tasks-ClearTpm
description: Microsoft-Windows-TPM-Tasks-ClearTpm
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 05/02/2017
ms.topic: article


---

# Microsoft-Windows-TPM-Tasks-ClearTpm

The `Microsoft-Windows-TPM-Tasks-ClearTpm` setting specifies whether to clear the Trusted Platform Module (TPM) during Windows setup.

Clearing the TPM prevents an issue in earlier versions that kept some Windows features from working if the TPM was incorrectly set.

## Value


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>0</em></p></td>
<td><p>Do not clear the TPM. Default value.</p></td>
</tr><tr class="even">
<td><p><em>1</em></p></td>
<td><p>Clear the TPM only when Windows has taken ownership of the TPM. </p></td>
</tr><tr class="odd">
<td><p><em>2</em></p></td>
<td><p>Always clear the TPM. </p></td>
</tr>
</tbody>
</table>

## Parent Hierarchy


[Microsoft-Windows-TPM-Tasks](microsoft-windows-tpm-tasks.md) | **ClearTpm**

## Valid Configuration Passes


Specialize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TPM-Tasks](microsoft-windows-tpm-tasks.md).

## XML Example


The following XML shows how to use the `<ClearTpm>` setting in an unattend file.

```
<?xml version="1.0" encoding="UTF-8"?>

-<unattend xmlns="urn:schemas-microsoft-com:unattend">


-<settings pass="specialize">


-<component language="neutral" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" versionScope="nonSxS" publicKeyToken="31bf3856ad364e35" processorArchitecture="amd64" name="Microsoft-Windows-TPM-Tasks">

<ClearTpm>2</ClearTpm>

</component>

</settings>

<cpi:offlineImage xmlns:cpi="urn:schemas-microsoft-com:cpi" cpi:source="wim:c:/wims/14993/install.wim#Windows 10 Pro Insider Preview"/>

</unattend>
```

