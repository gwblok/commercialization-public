---
title: CountryOrRegion
description: CountryOrRegion
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5774e2db-41da-4ee8-873c-e34183fb29d7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# CountryOrRegion


`CountryOrRegion` specifies the geo-code for this location. This code is not the same as the country code that is used for dialing.

Region codes change over time. To find the latest region codes, follow these steps:

1.  Create a registry key that has a list of region codes by using the **Phone and Modem** item in Control Panel. To do this, follow these steps:

    1.  On your technician computer, use the **Run** command to open **telephon.cpl**. This opens the **Phone and Modem** Control Panel. The first time this Control Panel item is opened, a dialog box opens and prompts you for location details. If this dialog box does not appear, close the **Phone and Modem** Control Panel, and then continue to step 2.

    2.  Follow the on-screen prompts to enter the location information. After you have set the location information, the system writes a registry key that has an updated list of region code values.

2.  Find the list of region codes in the registry. To do this, follow these steps:

    1.  Use the **Run** command to open **regedit**. This open Registry Editor.

    2.  In Registry Editor, navigate to the **Computer\\HKEYLOCALMACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Telephony\\Country List** registry key. This registry key shows the current list of region code identifiers.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Region_code</em></p></td>
<td><p>Specifies the region code. <em>Region_code</em> is an integer.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[microsoft-windows-tapisetup-](microsoft-windows-tapisetup.md) | [TapiUnattendLocation](microsoft-windows-tapisetup-tapiunattendlocation.md) | **CountryOrRegion**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-tapisetup-](microsoft-windows-tapisetup.md).

## XML Example


The following example shows how to set the location that you are calling from.

```
<TapiUnattendLocation>
   <AreaCode>123</AreaCode>
   <CountryOrRegion>246</CountryOrRegion>
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

 

 







