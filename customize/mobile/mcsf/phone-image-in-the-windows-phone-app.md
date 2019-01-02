---
title: Phone image in the phone app
description: OEMs can replace the default images of the phone that appears in the phone app.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 170a5556-9902-4efb-84d6-41d5901ff33e


ms.date: 05/02/2017
ms.topic: article


---

# Phone image in the phone app


OEMs can replace the default images of the phone that appears in the phone app. These images are included in the OEMImage.cab that is provided in this customization sample. The OEM can replace these images with custom ones that more accurately depict their phone. When the OEM provides a new image, this image will be used and will replace the OEMavatar.cab file that is used by default.

**Limitations and restrictions:**

The custom image files to represent the phone must meet the following specifications:

-   PNG24

-   RGB

-   Bicubic

-   96 DPI

-   Alpha background transparency

-   Dimensions - Height (width varies by device):

    800 px

    400 px

    200 px

    150 px

    120 px

    80 px

-   The image must be the exact height and width of the device with no padding.

-   Match the orientation and general creative style of the sample image. To avoid issues associated with the localization of the screen image text, the phone image must depict a phone that is turned off.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Complete the following steps to create a cab file containing six custom .png image files to represent the phone.

    1.  Create the six custom phone images and place them in a folder named OEMImage.

    2.  Create a new OEMImage.cab file that contains your custom images using Makecab.exe, which is a utility included with Windows. To do this:

        1.  Create a directive file for Makecab.exe with the filename OEMImage.ddf.

            The .ddf file must have the following contents:

            ```
            ;*** OEMImage.ddf example
            ;
            .OPTION EXPLICIT     ; Generate errors 
            .Set CabinetNameTemplate=OEMImage.cab
            .set DiskDirectoryTemplate=CDROM ; All cabinets go in a single directory
            .Set UniqueFiles="OFF"
            .Set Cabinet=on
            .Set DiskDirectory1=OEMImage.CAB
            DeviceImage_80.png
            DeviceImage_120.png
            DeviceImage_150.png
            DeviceImage_200.png
            DeviceImage_400.png
            DeviceImage_800.png
            ```

        2.  Place the OEMImage.ddf file in the OEMImage folder along with the six .png image files. At a command-line prompt in the OEMImage folder, run the following command:

            ```
            Makecab.exe /F OEMImage.ddf
            ```

            This produces a .cab file called OEMImage.cab.

2.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="WindowsPhoneAppImage"  
                         Description="Use to replace the default images of the phone that appears in the Windows Phone app."
                         Owner=""  
                         OwnerType="OEM"> 

       <Static>

          <Settings Path="MediaTransferProtocol/DeviceAssets">  
             <!-- Use to add the .cab containing the PNG image files that depict the phone at various sizes and the OEMImage.ddf -->
             <Asset Name="DeviceImageCab" Source="C:\Path\OEMImage.cab" />
             
             <!-- Use to specify which device image .cab should be used to display images of the phone in the Windows Phone app -->
             <Setting Name="Avatar" Value="OEMImage.cab" /> 
          </Settings>  

       </Static>

    </ImageCustomizations>
    ```

3.  Specify an `Owner`.

4.  Add the OEMImage.cab file to the customization package. To do this:

    1.  Set the asset `Name` to **DeviceImageCab**.

    2.  Specify the location of the OEMImage.cab on your workstation by changing *C:\\Path\\* in the `Source` attribute to match the location of OEMImage.cab.

5.  Specify which device image .cat to use when displaying images of the phone in the Windows Phone app by setting the `Avatar` value to OEMImage.cab.

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a phone.

2.  On the computer, install the Windows 10 Mobile app.

3.  Connect the phone to the computer using a USB cable.

4.  On the computer, open the mobile app.

5.  Verify that the phone image that you included in the build is visible in the mobile app.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
