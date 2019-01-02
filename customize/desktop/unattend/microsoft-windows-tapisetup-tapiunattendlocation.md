---
title: TapiUnattendLocation
description: TapiUnattendLocation
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 86aeb8bd-8ef1-44cf-82cb-fa779c2aa26c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# TapiUnattendLocation

`TapiUnattendLocation` specifies unattended installation settings for a telephony location.

If one of the child elements is not applicable in your country or region, you must specify an empty string in the unattended installation answer file, by entering two quotation marks (**""**).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [AreaCode](microsoft-windows-tapisetup-tapiunattendlocation-areacode.md) | Specifies the local telephone area code. |
| [CountryOrRegion](microsoft-windows-tapisetup-tapiunattendlocation-countryorregion.md) | Specifies the region ID for this location. This not the same as the country or region code used for dialing. |
| [DisableCallWaiting](microsoft-windows-tapisetup-tapiunattendlocation-disablecallwaiting.md) | Specifies the number to dial to disable call waiting. |
| [InternationalCarrierCode](microsoft-windows-tapisetup-tapiunattendlocation-internationalcarriercode.md) | Specifies the international telephone carrier. |
| [LongDistanceAccess](microsoft-windows-tapisetup-tapiunattendlocation-longdistanceaccess.md) | Specifies the number to dial from this location for long distance access. |
| [LongDistanceCarrierCode](microsoft-windows-tapisetup-tapiunattendlocation-longdistancecarriercode.md) | Specifies the long distance carrier. |
| [Name](microsoft-windows-tapisetup-tapiunattendlocation-name.md) | Specifies the name of this location. This appears in the user interface (UI). |
| [OutsideAccess](microsoft-windows-tapisetup-tapiunattendlocation-outsideaccess.md) | Specifies the number to dial to access an outside line from this location. |
| [PulseOrToneDialing](microsoft-windows-tapisetup-tapiunattendlocation-pulseortonedialing.md) | Specifies whether to use pulse dialing or tone dialing. |

## Valid Configuration Passes

specialize

## Parent Hierarchy

[Microsoft-Windows-TAPISetup](microsoft-windows-tapisetup.md) | **TapiUnattendLocation**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-tapisetup-](microsoft-windows-tapisetup.md).

## XML Example

The following XML output shows how to set the location from which you are calling.

```XML
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

[Microsoft-Windows-TAPISetup](microsoft-windows-tapisetup.md)
