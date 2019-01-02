---
title: Cellular data fallback when in limited Wi-Fi connectivity
description: OEMs can change the default behavior for the device when Wi-Fi connectivity becomes limited.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0a5587e9-3e1a-424f-8a89-a9303b71d944


ms.date: 05/02/2017
ms.topic: article


---

# Cellular data fallback when in limited Wi-Fi connectivity


OEMs can change the default behavior for the device when Wi-Fi connectivity becomes limited.

By default, if the device is connected to a Wi-Fi network and the data connection to a site is unsuccessful due to limited Wi-Fi connectivity, the device will complete the connection to the site using available cellular data networks (when possible) to provide an optimal user experience.

OEMs can change this default behavior so that the device does not use cellular data when Wi-Fi connectivity becomes limited. When the customization is enabled, a user option to use or not use cellular data for limited Wi-Fi connectivity becomes visible in the **Cellular & SIM** settings screen. This option is automatically set to **don’t use cellular data** when the customization is enabled.

**Note**  
Changing the default behavior may negatively impact the user experience.

 

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="CellularFailover"  
                         Description="Use to allow or disallow cellular data fallback when in limited Wi-Fi connectivity."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Cellcore/PerDevice/CellData">  
          <Setting Name="CellularFailOver" Value="" />       
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `CellularFailover` to one of the following:

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
    <td><p>0 or 'Failover is not allowed'</p></td>
    <td><p>Disables cellular data fallback when in limited Wi-Fi connectivity. This also sets the <strong>For limited Wi-Fi connectivity</strong> option in the <strong>Cellular &amp; SIM</strong> settings screen to <strong>don’t use cellular data</strong>.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Failover is allowed'</p></td>
    <td><p>Enables cellular data fallback when in limited Wi-Fi connectivity.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device with a UICC.

2.  If you set `CellularFailover` to 0 or 'Failover is not allowed', navigate to the **Cellular & SIM** settings screen and verify that the **don’t use cellular data** option is chosen as the default under **For limited Wi-Fi connectivity.**

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
