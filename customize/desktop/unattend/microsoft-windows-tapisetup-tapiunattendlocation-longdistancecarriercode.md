---
title: LongDistanceCarrierCode
description: LongDistanceCarrierCode
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b3d12735-2359-47be-b660-cf7d06fa4ee1
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# LongDistanceCarrierCode


`LongDistanceCarrierCode` specifies the number to dial to access the long distance carrier for your current location.

If this element is not applicable in your country or region, enter an empty string in the unattended installation answer file by entering two quotation marks (**""**).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Long_distance_carrier_code</em></p></td>
<td><p>Specifies the long distance carrier code. <em>Long_distance_carrier_code</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-tapisetup-](microsoft-windows-tapisetup.md) | [TapiUnattendLocation](microsoft-windows-tapisetup-tapiunattendlocation.md) | **LongDistanceCarrierCode**

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

 

 







