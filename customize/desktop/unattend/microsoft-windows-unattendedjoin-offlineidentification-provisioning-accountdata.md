---
title: AccountData
description: AccountData
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: A437953E-2D78-4183-89F1-1F1F36121427
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# AccountData


`AccountData` specifies account data used when joining a domain.

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


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md) | [OfflineIdentification](microsoft-windows-unattendedjoin-offlineidentification.md) | [Provisioning](microsoft-windows-unattendedjoin-offlineidentification-provisioning.md) | **AccountData**

## Applies To


Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-UnattendedJoin](microsoft-windows-unattendedjoin.md).

## XML Example


The following XML output shows how to set the Provisioning settings.

```
<OfflineIdentification>
   <Provisioning>
      <AccountData>BASE64-ENCODED-BLOB</AccountData>   
   </Provisioning>
</OfflineIdentification>
```

 

 






