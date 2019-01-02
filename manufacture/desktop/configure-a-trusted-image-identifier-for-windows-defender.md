---

Description: Configure a Trusted Image Identifier for Windows Defender
ms.assetid: b55f681f-94d7-4800-a927-ec186dc046e2
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Configure a Trusted Image Identifier for Windows Defender

ms.date: 05/02/2017
ms.topic: article


---

# Configure a Trusted Image Identifier for Windows Defender

Make your devices work faster right out of the box by adding a trusted image identifier to Windows Defender. 

You can speed up the initial performance of your PCs and devices for the end user by adding a trusted image identifier to Windows Defender. Windows Defender can help to prevent, remove, and quarantine malware and spyware.

By default, Windows Defender performs a scan of each file on the device when the device accesses the file for the first time. This is known as an on-access scan. Optimization mechanisms, such as caching, help reduce unnecessary scans of files that have already been scanned. When Windows Defender performs a quick scan or a full scan (also known as on-demand scans), the rest of the files on the system will be marked as safe.

**Note**  
If you have already deployed a series of devices, and then later determine that there is a potential problem with the security of the image, contact your Depth Project Manager (PM) within the Windows Ecosystem Engagement team. and provide the unique identifier of the image. Microsoft will add this unique identifier into Windows Update. After a device with that unique identifier receives updates from Windows Update, Windows Defender performs scans on all of the files on that device.

## <span id="Adding_a_Trusted_Image_Identifier"></span><span id="adding_a_trusted_image_identifier"></span><span id="ADDING_A_TRUSTED_IMAGE_IDENTIFIER"></span>Adding a Trusted Image Identifier

For optimal performance, we recommend that you add this setting when you prepare the device for final deployment, after you perform a full scan of the final image.

**To add a trusted image identifier**

1. Create a Windows Setup answer file (unattend.xml), and add the `Security-Malware-Windows-Defender\TrustedImageIdentifier` setting. To learn more, see the OEM deployment lab: [Customize Windows with an answer file](https://docs.microsoft.com/windows-hardware/manufacture/desktop/oem-deployment-of-windows-10-for-desktop-editions#customize-windows-with-an-answer-file).

2.  For the `TrustedImageIdentifier` setting, specify a unique identifier for the image, such as a GUID or other unique value (example: "Contoso Laptop Model 1 2018-07-31").

3. [Apply the image to a new device, and boot it into audit mode](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/oem-deployment-of-windows-10-for-desktop-editions#deploy-your-images-to-a-new-pc), and scan the image by using Windows Defender or another scanning tool. This can help make sure that the image is safe. 

4. Reseal the image, adding the answer file with the TrustedImageIdentifier setting.

   ```
   C:\Windows\System32\Sysprep\sysprep /oobe /generalize /unattend:c:\recovery\oem\Unattend.xml /shutdown
   ```

4. Apply the image to new devices, and deliver them to customers.

   The next time that the device starts, Windows identifies all of the files currently on the system, and skips these files during subsequent scans.

## <span id="related_topics"></span>Related topics

[Use Answer Files with Sysprep](use-answer-files-with-sysprep.md#bkmk_1)
