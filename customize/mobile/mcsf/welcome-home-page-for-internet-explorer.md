---
title: Welcome home page for Microsoft Edge
description: Welcome home page for Microsoft Edge
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8a012b90-1150-4ee3-9fa4-b5979cc6f149


ms.date: 05/02/2017
ms.topic: article


---

# Welcome home page for Microsoft Edge


Partners can set the home page that appears the first time that Microsoft Edge is opened. This page is only shown the first time the browser is opened. After that, the browser displays either the most recently viewed page or an empty page if the user has closed all tabs or opens a new tab.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample or use the sample WelcomeHomePage.xml file.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="WelcomeHomePage"  
                         Description="Use to set the home page that appears the first time that Microsoft Edge is opened."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        <Settings Path="InternetExplorer">  
          <Setting Name="FirstRunUrl" Value="" />
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Specify the `FirstRunUrl``Value` with a valid link that starts with `http://`. It is recommended that you use a forward link that redirects the user to a localized page.

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a phone with a data connection or Wi-Fi connection enabled.

2.  Open Microsoft Edge, and verify that the correct page appears.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
