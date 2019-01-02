---
title: Customizations for maps
description: Describes the customizations that you can configure for maps on the mobile device.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: fcb16b44-8000-4913-adec-c564975513ce


ms.date: 05/02/2017
ms.topic: article


---

# Customizations for maps


Describes the customizations that you can configure for maps on the mobile device.

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
<td><p><a href="map-data-on-an-sd-card-and-map-preload.md" data-raw-source="[Map data on an SD card and map preload](map-data-on-an-sd-card-and-map-preload.md)">Map data on an SD card and map preload</a></p></td>
<td><p>Map data is used by the Maps application and the map control for third-party applications. OEMs can choose to store this data on an SD card, which provides the advantage of saving internal memory space for user data and allows the user to download more offline map data. Microsoft recommends enabling the <strong>UseExternalStorage</strong> setting on phones with less than 8 GB of user storage and has an SD card slot.</p></td>
</tr>
<tr class="even">
<td><p><a href="maps-for-phones-shipped-in-china.md" data-raw-source="[Maps for phones shipped in China](maps-for-phones-shipped-in-china.md)">Maps for phones shipped in China</a></p></td>
<td><p>Microsoft recommends using the <a href="https://docs.microsoft.com/en-us/windows/configuration/wcd/wcd-maps#chinavariantwin10" data-raw-source="[ChinaVariantWin10](https://docs.microsoft.com/en-us/windows/configuration/wcd/wcd-maps#chinavariantwin10)">ChinaVariantWin10</a> setting instead of this legacy MCSF setting.</p>
<p>For a Windows mobile device shipping in China, partners must specify that the device is intended for that market by configuring <code>ChinaVariant</code> setting. When enabled, maps approved by the State Bureau of Surveying and Mapping in China are used and the maps are obtained from a server located in China.</p></td>
</tr>
<tr class="odd">
<td><p><a href="preloaded-map-data-in-the-user-store.md" data-raw-source="[Preloaded map data in the user store](preloaded-map-data-in-the-user-store.md)">Preloaded map data in the user store</a></p></td>
<td><p>OEMs can choose a single map region to preload from the multiple regions that are available for OEMs to download from the Microsoft partner site(s) where the Kits are also available. OEMs can choose to store this data in the user store. Maps are grouped into regions, but there are some restrictions. For more information about these restrictions, see the accompanying instructions that are part of the map data download on the Microsoft partner site(s).</p></td>
</tr>
<tr class="even">
<td><p><a href="temporary-map-data-cache-size.md" data-raw-source="[Temporary map data cache size](temporary-map-data-cache-size.md)">Temporary map data cache size</a></p></td>
<td><p>When a user attempts to view map data for a location that was not preloaded or is not already installed on the phone, map data will be downloaded to dynamically render a map. This data is stored in a temporary cache that the Maps application maintains for this purpose. By default this cache is allowed to use a maximum of 128 MB of storage. For phones with a limited amount of available storage, OEMs can specify that the cache only use a maximum of 64 MB of storage. Microsoft recommends that this customization only be used for phones with a limited amount of internal storage space. Reducing the size of the online cache for Map data does not affect the size of the installed (or offline) maps.</p></td>
</tr>
</tbody>
</table>

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
