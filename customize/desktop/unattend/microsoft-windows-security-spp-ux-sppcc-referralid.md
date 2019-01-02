---
title: ReferralId
description: ReferralId
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 534074f5-dd61-4d77-bb7c-5b4de177d688
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ReferralId


`ReferralId` specifies the identity of an OEM participating in the Windows Anytime Upgrade reward program.

**Important**  
This setting is deprecated.

This information is for reference only.

 

For information about the Windows Anytime Upgrade program, see [Windows Anytime Upgrade](http://go.microsoft.com/fwlink/?LinkId=142336).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>ReferralID</em></p></td>
<td><p>Specifies the identity of OEMs participating in the Windows Anytime Upgrade program.</p>
<p>The default value is <strong>00000</strong>.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


auditSystem

oobeSystem

specialize

## Parent Hierarchy


[microsoft-windows-security-spp-ux-sppcc-](microsoft-windows-security-spp-ux-sppcc.md) | **ReferralId**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-security-spp-ux-sppcc-](microsoft-windows-security-spp-ux-sppcc.md).

## XML Example


The following XML output shows how to set Windows Anytime Upgrade.

```
<ReferralId>12345</ReferralId>
```

## Related topics


[microsoft-windows-security-spp-ux-sppcc-](microsoft-windows-security-spp-ux-sppcc.md)

 

 







