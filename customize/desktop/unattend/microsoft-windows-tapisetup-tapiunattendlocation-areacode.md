---
title: AreaCode
description: AreaCode
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ba2356c3-afb6-4b60-8717-1f052adbb67f
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# AreaCode


`AreaCode` specifies the local area code of this location.

If this element is not applicable in your country or region, enter an empty string in the unattended installation answer file by entering two quotation marks (**""**).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Area_code</em></p></td>
<td><p>Specifies the local area code. <em>Area_code</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-tapisetup-](microsoft-windows-tapisetup.md) | [TapiUnattendLocation](microsoft-windows-tapisetup-tapiunattendlocation.md) | **AreaCode**

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

 

 







