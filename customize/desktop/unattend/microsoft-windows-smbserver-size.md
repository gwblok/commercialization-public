---
title: Size
description: Size
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2ccf08d0-7b88-42b6-b519-4ceb3175557a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Size


`Size` specifies the size of the cache.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>1</strong></p></td>
<td><p>Specifies that memory use is minimized.</p></td>
</tr>
<tr class="even">
<td><p><strong>2</strong></p></td>
<td><p>Specifies that the computer balances memory usage with network performance.</p></td>
</tr>
<tr class="odd">
<td><p><strong>3</strong></p></td>
<td><p>Specifies that memory use is maximized for file sharing and throughput of network applications. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
In earlier releases, the default was **1** for clients and **3** for servers.

 

## Parent Hierarchy


[Microsoft-Windows-SMBServer](microsoft-windows-smbserver.md) | **Size**

## Valid Configuration Passes


generalize

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-SMBServer](microsoft-windows-smbserver.md).

## XML Example


The following XML output shows how to specify that the computer balances memory usage with network performance.

```
<LmAnnounce>true</LmAnnounce>
<Size>2</Size>
```

## Related topics


[Microsoft-Windows-SMBServer](microsoft-windows-smbserver.md)

 

 







