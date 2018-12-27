---
title: AccountData
description: AccountData
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3a2fbe8c-3704-4aab-8756-ef8e8ea2249c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# AccountData


`AccountData` specifies account data used when joining a domain.

**Note**  
Use either [Provisioning](microsoft-windows-unattendedjoin-identification-provisioning.md) or [Credentials](microsoft-windows-unattendedjoin-identification-credentials.md) to join an account to the domain. The settings in Provisioning will be used to join the account to the domain, if values are entered for both the Provisioning and Credentials settings.

 

For information about joining a domain using Provisioning, see the MSDN topic, [NetJoin](http://go.microsoft.com/fwlink/?LinkId=124095).

To generate the `AccountData` information:

1.  Use the command:

    **djoin.exe** /provision /domain domainname /machine machinename /savefile filename

    Example:

    ```
    djoin.exe /provision /domain contoso.com /machine machinename /savefile AccountData.txt
    ```

2.  Copy and paste the contents of AccountData.txt to the answer file.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>AccountData</em></p></td>
<td><p>Specifies account data used when joining a domain.</p>
<p><em>AccountData</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [Identification](microsoft-windows-unattendedjoin-identification.md) | [Provisioning](microsoft-windows-unattendedjoin-identification-provisioning.md)| **AccountData**

## Applies To


For a list of Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example


The following XML output shows how to set the Provisioning settings.

```
<Identification>
<Provisioning>
<AccountData>BASE64-ENCODED-BLOB</AccountData>
</Provisioning>
</Identification>
```

## Related topics


[Provisioning](microsoft-windows-unattendedjoin-identification-provisioning.md)

 

 







