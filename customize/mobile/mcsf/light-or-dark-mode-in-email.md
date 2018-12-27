---
title: Light or dark mode in email
description: The email application consists of several screens, including the List View, Settings, Automatic Replies, Search, Inbox Linking, Read, and Compose.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 81ec5d29-1be6-4fbc-81aa-39ccb04087ba


ms.date: 05/02/2017
ms.topic: article


---

# Light or dark mode in email


The email application consists of several screens, including the List View, Settings, Automatic Replies, Search, Inbox Linking, Read, and Compose. By default, the email background for all pages except Read and Compose match the system theme. The Read and Compose pages always have a light background. Partners can specify that the entire email application always has a light background, but users do not have access to this setting. However, if the user turns on high-contrast mode, it overrides all other settings, and all screens use the high contrast settings.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DefaultEmailBackgroundTheme"  
                         Description="Use to configure the entire email app to always have a light background."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        <Settings Path="Email">  
          <Setting Name="DefaultBackgroundThemeSetting" Value="" />
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `DefaultBackgroundThemeSetting` to one of the following values:

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
    <td><p>1 or Light Background</p></td>
    <td><p>Configures the entire email application to always have a light background.</p>
    <p>Users cannot override this setting, but if high contrast is enabled this setting will be changed.</p></td>
    </tr>
    <tr class="even">
    <td><p>0 or System Default</p></td>
    <td><p>Keeps the default background theme for the email app.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a phone that has data connectivity.

2.  Go to the **theme** screen in **Settings**. Set the background theme to dark.

3.  Go to the **email+accounts** screen in **Settings**. Configure an email account.

4.  Go to the configured email account’s inbox.

5.  Verify that the email background is light.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
