---
title: Maps for phones shipped in China
description: Microsoft recommends using the ChinaVariantWin10 setting instead of this legacy MCSF setting.For a Windows mobile device shipping in China, partners must specify that the device is intended for that market by configuring ChinaVariant setting.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d3723ee6-3615-4ebd-bc34-274fe5c2e452


ms.date: 05/02/2017
ms.topic: article


---
# Maps for phones shipped in China

Microsoft recommends using the [ChinaVariantWin10](https://docs.microsoft.com/en-us/windows/configuration/wcd/wcd-maps#chinavariantwin10) setting instead of this legacy MCSF setting.

For a Windows mobile device shipping in China, partners must specify that the device is intended for that market by configuring `ChinaVariant` setting. When enabled, maps approved by the State Bureau of Surveying and Mapping in China are used and the maps are obtained from a server located in China.

This customization may result in different maps, servers, or other configuration changes on the device.

> [!Note]
> If partners do not set the `ChinaVariant` setting to 1, partners may not ship the device in China.

## <a href="" id="constraints---none"></a>Constraints

None

## <a href="" id="instructions-"></a>Instructions

1. Create a customization answer file using the contents shown in the following code sample or use the sample MapsForChina.xml file.

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"
                         Name="MapsForChina"
                         Description="Use to specify that the device is instended for shipping in China. When enabled, maps approved by the State Burue of Surveying and Mapping
                                     and mapping in China are used and the maps are obtained froma  server located in China."
                        Owner=""
                        OwnerType="OEM">
     <Static>
       <Settings Path="Maps">
         <!-- Set to 0 or 'No' (to disable), or set to 1 or 'Yes' (to enable maps for China) -->
         <Setting Name="ChinaVariant" Value="" />
       </Settings>
     </Static>
   </ImageCustomizations>
   ```

1. Specify an `Owner`.
1. Set `ChinaVariant` to one of the following values:

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
    <td><p>1 or Yes</p></td>
    <td><p>Maps approved by the State Bureau of Surveying and Mapping in China are used and the maps are obtained from a server located in China.</p></td>
    </tr>
    <tr class="even">
    <td><p>0 or No</p></td>
    <td><p>Disables the feature.</p></td>
    </tr>
    </tbody>
    </table>

## <a href="" id="testing-"></a>Testing

1. Flash the build containing this customization to a phone with a UICC.
1. Launch the maps application and verify that the maps used are the same as those approved by the State Bureau of Surveying and Mapping in China.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
