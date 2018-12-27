---
title: Override the default CountryTable.xml
description: The mobile runtime configuration package includes a built-in XML file (CountryTable.xml) for mapping between GeoIDs, iso3166 country/region codes, and MCCs.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e5d9f6f4-846f-4bde-a33f-fb98b573bc18


ms.date: 05/02/2017
ms.topic: article


---

# Override the default CountryTable.xml


The mobile runtime configuration package includes a built-in XML file (CountryTable.xml) for mapping between GeoIDs, iso3166 country/region codes, and MCCs. Windows uses this table to assist in validating 3-digit MNCs for specific countries/regions, which is done by including an MNC list for that country/region. Otherwise, the OS assumes that MNCs are valid if they are 2 digits.

OEMs can override the default country/region lookup table and instruct the runtime configuration engine to use an OEM-provided mapping table instead.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="OverrideDefaultCountryLookup"  
                         Description="Use to override the default country/region lookup table (CountryTable.xml) with the OEM mapping table."
                         Owner=""  
                         OwnerType="OEM"> 

       <Static>

          <Settings Path="Multivariant"> 
             <Setting Name="OverrideDefaultCountryLookup" Value="" /> 
          </Settings>  

       </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value for `OverrideDefaultCountryLookup` to one of the following values:

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Value</th>
    <th>Description</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>0</p></td>
    <td><p>Use the default country/region lookup table, CountryTable.xml, used by the OS.</p></td>
    </tr>
    <tr class="even">
    <td><p>1</p></td>
    <td><p>Override the default country/region lookup table and use an OEM provided mapping table.</p></td>
    </tr>
    </tbody>
    </table>

     

4.  If the value for `OverrideDefaultCountryLookup` is set to 1, the OEM must include their custom countrytable.xml file in a package and place this file in the %systemdrive%\\programs\\commonfiles\\adc\\OEM directory.

    OEMs who provide their own country/region lookup table must use the following format for the XML file:

    ```XML
    <countrytable>
       <country mcc="202" iso3166="GR" GeoID="98"/>        <!-- Greece -->
       <country mcc="204" iso3166="NL" GeoID="176"/>       <!-- Netherlands -->
       <!-- And so on -->
       <country mcc="316" iso3166="US" GeoID="244">        <!-- United States-->
          <mnclist>
             <mnc id="010"/>
             <mnc id="011"/>
          </mnclist>
       </country>
       <!-- And so on -->
    </countrytable>
    ```

<a href="" id="testing-"></a>**Testing:**  
Work with your mobile operator partners to test this customization on their networks.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
