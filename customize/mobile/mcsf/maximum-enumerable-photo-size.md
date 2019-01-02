---
title: Maximum enumerable photo size
description: For phones that have the hardware capability to capture various resolutions, partners can specify the resolution limit for photos that can be accessed by third party apps.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8001faaa-c6da-4bc6-b963-5d6971ced7f2


ms.date: 05/02/2017
ms.topic: article


---

# Maximum enumerable photo size


For phones that have the hardware capability to capture various resolutions, partners can specify the resolution limit for photos that can be accessed by third party apps.

Only OEM applications have access to the maximum resolution limit.

**Note**  
This customization is only used by the **Windows.Phone.Media.Capture** service, which is provided in Windows Phone 8.1 for backwards compatibility only. **Windows.Media.Capture** does not support this customization.

 

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="MaximumEnumerablePhotoSize"  
                         Description="On phones that can capture multiple resolutions, use to specify the resolution limit for photos
                                      that can be accessed by third party apps."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

       <Settings Path="Camera">  
          <Setting Name="MaximumEnumerablePhotoSize" Value="" />  
       </Settings> 

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value for `MaximumEnumerablePhotoSize` to the photo resolution in pixels. For example, to set 5 megapixels as the maximum enumerable photo size, set `Value` to 5242880 (decimal) or 0x500000 (hexadecimal).

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a phone that has the hardware capability you are testing.

2.  Run a test using the [PhotoCaptureDevice.GetAvailableCaptureResolutions](http://go.microsoft.com/fwlink/p/?LinkId=286325) method and check if resolutions higher than the value you specified for `MaximumEnumerablePhotoSize` have been filtered out.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
