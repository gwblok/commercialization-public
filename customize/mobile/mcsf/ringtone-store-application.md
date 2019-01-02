---
title: Ringtone store application
description: Partner apps can be used to sell ringtones to users.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 05b7df91-be48-4aaf-bf63-cbc3ced0fa28


ms.date: 05/02/2017
ms.topic: article


---

# Ringtone store application


Partner apps can be used to sell ringtones to users. The app owner must provide the service for the ringtone catalog and to manage downloads. Users are shown an option to **Get more** ringtones in the ringtone picker, from which they can automatically launch the ringtone store application.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create an application that supports ringtones. For more information on how to do this, see *How to use the save ringtone task for Windows Phone* in the Windows Phone SDK Documentation.

2.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="RingtoneStoreApp"  
                         Description="Use to enable users to automatically launch the ringtone store application that was created by
                                      the partner to sell ringtones to users."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <!-- Preload the ringtone store app. Specify the source, license, and ProvXML files. -->
        <Applications>
          <Application Source=""
                       License=""
                       ProvXML="" />
        </Applications>

        <Settings Path="EventSounds">  
          <Setting Name="GetMoreRingtonesLink" Value="app://" />
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

3.  Specify an `Owner`.

4.  Preload your ringtone store app. To do this:

    1.  Set `Source` to the location and file name of your .xap or .appx. For example, *C:\\Path\\ContosoRingtoneStoreApp.xap*.

    2.  Set `License` to the location and name of the app license file. For example, *C:\\Path\\ContosoRingtoneStoreAppLicense.xml*.

    3.  Set `ProvXML` to the location and name of the provXML file. For example, *C:\\Path\\mpap\_oemapp\_01.provxml*.

5.  Set the value of `GetMoreRingtonesLink` your application ID preceded by the **app://** prefix. For example, if your app ID is *{5B04B775-356B-4AA0-AAF8-6491FFEA5605}*, you must set the value to `app://5B04B775-356B-4AA0-AAF8-6491FFEA5605`. You may also set it to `app://5B04B775-356B-4AA0-AAF8-6491FFEA5605/_default`.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a phone.

2.  Go to the **Sounds** screen in **Settings**.

3.  Select the **Ringtone** picker.

4.  In the ringtone picker screen, scroll to the bottom and verify that the **Get more** link is visible.

5.  Tap the link and confirm that it launches your ringtone store application.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
