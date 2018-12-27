---
title: Customizations for device management
description: This section provides more information about device management settings that OEMs can change.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8389d4a3-04b8-4bd5-9079-d6f47d4bc60b


ms.date: 05/02/2017
ms.topic: article


---

# Customizations for device management


This section provides more information about device management settings that OEMs can change.

## In this section


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Topic</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="enabling-runtime-configuration.md" data-raw-source="[Enabling runtime configuration](enabling-runtime-configuration.md)">Enabling runtime configuration</a></p></td>
<td><p>Runtime configuration, or multivariant, provides a generic mechanism for creating a single image that can work for multiple markets and reduce the number of images that OEMs need to create, manage, and test. By default, runtime configuration is enabled and ADC is turned off. Only one or the other must be turned on. So, if an OEM wants to disable runtime configuration, they must enable ADC.</p>
<p>The OS will handle different scenarios depending on whether runtime configuration has been enabled so OEMs should take into consideration the scenarios they are trying to enable.</p></td>
</tr>
<tr class="even">
<td><p><a href="managing-runtime-configuration-data.md" data-raw-source="[Managing runtime configuration data](managing-runtime-configuration-data.md)">Managing runtime configuration data</a></p></td>
<td><p>OEMs can configure the following settings to manage the cleanup of runtime configuration data on the mobile device.</p></td>
</tr>
<tr class="odd">
<td><p><a href="override-the-default-countrytablexml.md" data-raw-source="[Override the default CountryTable.xml](override-the-default-countrytablexml.md)">Override the default CountryTable.xml</a></p></td>
<td><p>The mobile runtime configuration package includes a built-in XML file (CountryTable.xml) for mapping between GeoIDs, iso3166 country/region codes, and MCCs. Windows uses this table to assist in validating 3-digit MNCs for specific countries/regions, which is done by including an MNC list for that country/region. Otherwise, the OS assumes that MNCs are valid if they are 2 digits.</p>
<p>OEMs can override the default country/region lookup table and instruct the runtime configuration engine to use an OEM-provided mapping table instead.</p></td>
</tr>
<tr class="even">
<td><p><a href="setting-the-uicc-slot-for-branding-configuration.md" data-raw-source="[Setting the UICC slot for branding configuration](setting-the-uicc-slot-for-branding-configuration.md)">Setting the UICC slot for branding configuration</a></p></td>
<td><p>OEMs can specify which UICC slot will be used for branding configuration.</p></td>
</tr>
</tbody>
</table>

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
