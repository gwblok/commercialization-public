---
title: Default value for browser data saver
description: Partners can configure the default setting for the browser data saver feature by turning the browser optimization service on or off, using the BrowserDataSaver setting.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c94bf233-fb40-4386-939e-c4fc4ecb4cbb


ms.date: 05/02/2017
ms.topic: article


---
# Default value for browser data saver

Partners can configure the default setting for the browser data saver feature by turning the browser optimization service on or off, using the `BrowserDataSaver` setting.

<a href="" id="constraints---none"></a>**Constraints:** None

## Instructions

1. Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"
                         Name="BrowserDataSaver"
                         Description="Use to configure the default setting for the browser data saver feature."
                         Owner=""
                         OwnerType="OEM">
      <Static>
        <Settings Path="InternetExplorer/DataSaving">
          <Setting Name="BrowserDataSaver" Value="" />
       </Settings>
      </Static>
    </ImageCustomizations>
    ```

1. Specify an `Owner`.
1. Set `BrowserDataSaver` to one of the following values:

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
    <td><p>0 or 'Disabled'</p></td>
    <td><p>The browser data saver feature is turned off.</p>
    <p>The <strong>Data Sense savings</strong> option in the browser settings CPL is set to <strong>off</strong>.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Enabled'</p></td>
    <td><p>The browser data saver feature is turned on.</p>
    <p>The <strong>Data Sense savings</strong> option in the browser settings CPL is set to <strong>automatic</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Setting does not exist</p></td>
    <td><p>The browser data saver feature is turned on.</p>
    <p>The <strong>Data Sense savings</strong> option in the browser settings CPL is set to <strong>automatic</strong>.</p></td>
    </tr>
    </tbody>
    </table>

## Testing steps

1. Flash the build containing this customization to a device.
1. Open Microsoft Edge to launch the browser for the first time. Select **recommended** when the dialog to use the browser settings is displayed.
1. Go to the browser settings CPL.
1. Depending on the value that you set for `BrowserDataSaver`, verify:
   * If `BrowserDataSaver` is set to 0, verify that the **Data Sense savings** option is set to **off**.
   * If `BrowserDataSaver` is set to 1, verify that the **Data Sense savings** option is set to **automatic**.
   * If `BrowserDataSaver` setting has not been set, verify that the **Data Sense savings** option is set to **automatic**.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
