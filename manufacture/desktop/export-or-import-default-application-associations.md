---

Description: Export or Import Default Application Associations
ms.assetid: 87eb7510-df1a-4e3f-9cd4-5400fa6e1a07
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Export or Import Default Application Associations

ms.date: 11/14/2018
ms.topic: article

---

# Export or Import Default Application Associations

When building Windows 10 images, you can update the default programs associated with file name extensions or protocols. 

To do this, create an app association file and import it into your images using DISM. 

## Generate a default app associations XML File

Deploy your Windows image to a test computer and configure the programs that are included in your image. You can log into Windows and use Control Panel to select your default app associations. You can export the default app associations that you have configured to an XML file on a network share or removable media so that you can import them into the WIM or VHD file before you deploy it to your destination computers.

**Set default app associations**

1.  Install your Windows image to a test computer. For more information about how to apply a Windows image, see [Apply Images Using DISM](apply-images-using-dism.md).

2.  Start the test computer and complete Windows Setup.

3.  Open **Settings**. In **Find a setting**, search for and open **Default apps**.

4.  Configure default apps by file name extension or by app. For example, to set an installed photo viewing app as the default program that is used to open all of the file types and protocols that it supports, click **Set defaults by app**, select the photo viewing app > **Manage**, and then select the file types and associations for the app.

**Export default app association settings**

1.  On your test computer, open a Command Prompt as administrator. 

2.  Export the default app association settings from the test computer to an .xml file on a network share or USB drive:

    ```
    Dism /Online /Export-DefaultAppAssociations:"F:\AppAssociations.xml"
    ```

## <span id="add_or_remove_default_application_association_settings_to_a_windows_image"></span>Add or Remove Default Application Association Settings to a Windows Image


You can change the default app association settings in a WIM or VHD file before you deploy it to your destination computers. You can also add and remove default app association settings from an online image.

**Import default app association settings**

1.  On your technician computer, open a Command Prompt as administrator.

2.  Mount a Windows image from a WIM or VHD file:

    ```
    Dism /Mount-Image /ImageFile:C:\test\images\install.wim /Name:"Windows" /MountDir:C:\test\offline
    ```

3.  Import the .xml file that has the default app association settings to the Windows image:

    ```
    Dism.exe /Image:C:\test\offline /Import-DefaultAppAssociations:F:\AppAssociations.xml
    ```

**Review the default app association setting in an image**

1.  On your technician computer, open a Command Prompt administrator.

2.  List the app associations that have been applied to the mounted image:

    ```
    Dism.exe /Image:C:\test\offline /Get-DefaultAppAssociations
    ```

**Remove default app association settings**

1.  On your technician computer, open a Command Prompt as administrator.

2.  Remove the custom default app association that have been added to the mounted image:

    ```
    Dism.exe /Image:C:\test\offline /Remove-DefaultAppAssociations
    ```

**Unmount the Windows image**

1.  On your technician computer, open a Command Prompt as administrator.

2.  Unmount the image, committing changes:

    ```
    Dism /Unmount-Image /MountDir:C:\test\images\install.wim /commit
    ```
 
## Tips

* **Refresh this file with each major version**. Some recommended apps can manage more extensions with each new Windows 10 version available. It's a good practice to refresh your XML. For example, in Windows 10, version 1703, Microsoft Edge registers the epub extension. If you're using an XML file from Windows 10, version 1607, epub is missing. As a result, you will get an **An app default was reset** notification for epub.

* **Manually editing the file**: Don't just delete app associations you're not interested in. Otherwise on the first boot, the missing entries may trigger a flurry of notifications on the first boot saying "**An app default was reset**". 

  To prevent notifications, you can import multiple app association files. For example, you can import one file that includes all of the current Windows version's associations, and import your own separate file that includes a set of custom associations that you maintain one at a time. 
  
  1. From a new test computer, export a file that just includes the default file associations, for example, F:\1809-DefaultAppAssociations.xml.
  2. Modify your app associations as before, and export the file again. Use a text/XML editor to modify just the associations you're interested in, for example, F:\InternetExplorerAssociations.xml.
  3. Import both sets of associations into your images:
     ```
     Dism.exe /Image:C:\test\offline /Import-DefaultAppAssociations:F:\1809-DefaultAppAssociations.xml
     Dism.exe /Image:C:\test\offline /Import-DefaultAppAssociations:F:\InternetExplorerAssociations.xml
     ```
  
