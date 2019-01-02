---
title: Custom HTTP headers for Microsoft Edge
description: Partners can configure Microsoft Edge to send custom HTTP headers, in addition to the default HTTP headers, with all HTTP and HTTPS requests. The header is the portion of the HTTP request that defines the form of the message.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f308e57d-bf3e-4e43-b0a2-e89652771b9d


ms.date: 05/02/2017
ms.topic: article


---

# Custom HTTP headers for Microsoft Edge


Partners can configure Microsoft Edge to send custom HTTP headers, in addition to the default HTTP headers, with all HTTP and HTTPS requests. The header is the portion of the HTTP request that defines the form of the message.

**Limitations and restrictions**:

-   A maximum of 16 custom headers can be defined.

-   Custom headers cannot be used to modify the user agent string.

-   Each header must be no more than 1 KB in length.

The following header names are reserved and must not be overwritten:

-   Accept

-   Accept-Charset

-   Accept-Encoding

-   Authorization

-   Expect

-   Host

-   If-Match

-   If-Modified-Since

-   If-None-Match

-   If-Range

-   If-Unmodified-Since

-   Max-Forwards

-   Proxy-Authorization

-   Range

-   Referer

-   TE

-   USER-AGENT

-   X-WAP-PROFILE

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="CustomHTTPHeaders"  
                         Description="Use to configure Microsoft Edge to send custom HTTP headers."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        <Settings Path="InternetExplorer">  

          <!-- Use to configure Microsoft Edge custom HTTP header 1 -->
          <Setting Name="CustomHTTPHeaders1/$(ValueName)" Value="" />

          <!-- Use to configure Microsoft Edge custom HTTP header 2 -->
          <Setting Name="CustomHTTPHeaders2/$(ValueName)" Value="" />

          <!-- Use to configure up to 16 Microsoft Edge custom HTTP headers
          <Setting Name="CustomHTTPHeaders3/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders4/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders5/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders6/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders7/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders8/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders9/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders10/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders11/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders12/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders13/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders14/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders15/$(ValueName)" Value="" />
          <Setting Name="CustomHTTPHeaders16/$(ValueName)" Value="" />
          -->

        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Specify the value name for `CustomHTTPHeaders1` by replacing *$(ValueName)* with the *Header name* and set the `Value` to a *String*.

    *Header name* is the unique header name and *String* is the string that the header should pass for all HTTP and HTTPS requests.

4.  Specify additional custom headers, if needed. You can specify up to 16 custom HTTP headers.

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a phone.

2.  Tap on the Microsoft Edge tile to open the browser.

3.  Navigate to a site that mirrors the header information for HTTP requests, and verify that your headers appear as defined.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
