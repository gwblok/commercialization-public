---
title: LongDistanceAccess
description: LongDistanceAccess
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 840190fd-54d9-4ba4-bc0b-4516b864bbd3
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# LongDistanceAccess


`LongDistanceAccess` specifies the number to dial for placing an external, long-distance call from your current location.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Long_distance_access_code</em></p></td>
<td><p>Specifies the number to dial for placing an external, long-distance call. <em>Long_distance_access_code</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-tapisetup-](microsoft-windows-tapisetup.md) | [TapiUnattendLocation](microsoft-windows-tapisetup-tapiunattendlocation.md) | **LongDistanceAccess**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-tapisetup-](microsoft-windows-tapisetup.md).

## XML Example


The following XML output shows how to set the location from which you are calling.

```
<TapiUnattendLocation>
   <AreaCode>123</AreaCode>
   <CountryOrRegion>123</CountryOrRegion>
   <DisableCallWaiting>7</DisableCallWaiting>
   <InternationalCarrierCode>123456789</InternationalCarrierCode>
   <LongDistanceAccess>11</LongDistanceAccess>
   <LongDistanceCarrierCode>123456789</LongDistanceCarrierCode>
   <Name>MyLocation</Name>
   <OutsideAccess>9</OutsideAccess>
   <PulseOrToneDialing>1</PulseOrToneDialing>
</TapiUnattendLocation>
```

## Related topics


[TapiUnattendLocation](microsoft-windows-tapisetup-tapiunattendlocation.md)

 

 







