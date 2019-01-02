---

Description: Modify a Windows Image Using DISM
ms.assetid: f48b4681-bc59-4eb1-89c9-0163594467f7
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Modify a Windows Image Using DISM

ms.date: 04/24/2018
ms.topic: article


---
 
# Modify a Windows Image Using DISM

You can make changes to offline mounted or applied Windows images without booting into the operating system you're going to modify.

**Mounted** images are WIM, VHD, or FFU files that have their contents mapped to a folder. Changes to mounted images are made from either a Windows 10 technician PC, or from WinPE. You run run DISM commands against a mounted image, as well as run common file operations such as copying, pasting, and renaming on a mounted image. To save changes you make to the image, use the `/commit` option when you use DISM to unmount the image. To make changes to a mounted image, use `DISM /image:`.

**Applied** images are WIM, VHD, or FFU image files that have been applied to a specified partition. Offline changes to an applied image are usually performed from WinPE. To make changes to an applied image, use `DISM /image:`.

When you apply an image that you're going to recapture, apply the image to the root folder of a drive. If you recapture an image that wasn't applied to the root of a drive, the image will inherit the parent folder's security descriptors and might not be the same as what would be captured if the image was applied to the root of a drive.  See [Applying an image](https://docs.microsoft.com/windows-hardware/manufacture/desktop/capture-and-apply-windows-system-and-recovery-partitions#span-idapplyingtheimagespanspan-idapplyingtheimagespanspan-idapplyingtheimagespanapplying-the-image) to learn how to apply an image.

You can mount and modify multiple images on a single computer. For more information, see [Deployment Image Servicing and Management (DISM) Best Practices](deployment-image-servicing-and-management--dism--best-practices.md).

## <span id="Mounting_an_Image"></span><span id="mounting_an_image"></span><span id="MOUNTING_AN_IMAGE"></span>Mount an image

You can mount an image using the **/optimize** option to reduce initial mount time. However, When using the **/optimize** option, processes that are ordinarily performed during a mount will instead be completed the first time that you access a directory. As a result, there may be an increase in the time that is required to access a directory for the first time after mounting an image using the **/optimize** option.

1.  Open a command prompt with administrator privileges. 

    > [!Note]
    > If you are using a version of Windows other than Windows 8 or Windows 10, use the Deployment Tools Command Prompt that gets installed with the ADK.

2.  Use DISM to mount the image

    ```
    DISM /Mount-image /imagefile:<path_to_Image_file> {/Index:<image_index> | /Name:<image_name>} /MountDir:<target_mount_directory> [/readonly] /[optimize]}
    ```

    > [!Note]
    > To mount a Windows image from a VHD or FFU file, you must specify `/index:1`.

    For more information about the options available for the **/Mount-Image** option in DISM, see [DISM Image Management Command-Line Options](dism-image-management-command-line-options-s14.md).

## <span id="Modifying_an_Image"></span><span id="modifying_an_image"></span><span id="MODIFYING_AN_IMAGE"></span>Modify an Image

After you mount an image, you can use DISM to add and remove drivers, packages, language packs, enumerate drivers and packages, modify configuration settings, and more. 

### View and modify an image

You can create, view, and edit files on a mounted image, just as you would any other file on your PC. When you modify the files in a mounted image, those file changes get saved in the image. Note that although you can add application files and folders, you can't install applications directly into a mounted image in the same way that you would on a running PC. If you must add an application or a device, verify that you included all of the required files. 

### Add and remove drivers

See [Add and remove drivers to an offline Windows image](add-and-remove-drivers-to-an-offline-windows-image.md) to learn how to work with drivers. Note that the DISM driver commands will only run against an offline image.

### Add and remove packages

See [Add or remove packages offline using DISM](add-or-remove-packages-offline-using-dism.md) to learn how to work with packages.

### Add or remove languages

See [Add and remove language packs offline using DISM](add-and-remove-language-packs-offline-using-dism.md) to learn how to work with languages.

### <span id="Step_4__Upgrade_to_a_Higher_Edition_of_Windows"></span><span id="step_4__upgrade_to_a_higher_edition_of_windows"></span><span id="STEP_4__UPGRADE_TO_A_HIGHER_EDITION_OF_WINDOWS"></span>Upgrade to a higher Windows edition

Any changes you make to a mounted image are also applied to each potential target edition of Windows. Each target edition is staged in the image. The changes will not be lost when you upgrade to a higher edition of Windows. 

See [Change the Windows image to a higher edition using DISM](change-the-windows-image-to-a-higher-edition-using-dism.md) to learn how to change editions.

### <span id="Step_5__Reduce_the_Size_of_the_Image"></span><span id="step_5__reduce_the_size_of_the_image"></span><span id="STEP_5__REDUCE_THE_SIZE_OF_THE_IMAGE"></span>Reduce the Size of the Image

You can use DISM to reduce the footprint of a Windows image by cleaning up superseded components and resetting the base of the superseeded components.

-   At an elevated command prompt, run the following command to reduce the size of the image file:

    ```
    Dism /Image:C:\test\offline /cleanup-image /StartComponentCleanup /ResetBase 
    ```

## <span id="Committing_Changes_to_an_Image"></span><span id="committing_changes_to_an_image"></span><span id="COMMITTING_CHANGES_TO_AN_IMAGE"></span>Commit Changes to an Image

You can commit changes to an image without unmounting the image.

**To commit changes:**

-   At the administrator command prompt, type:

    ```
    Dism /Commit-Image /MountDir:C:\test\offline
    ```

    Use **/CheckIntegrity** to detect and track .wim file corruption when you commit changes to the image. When you apply or mount the image, use **/CheckIntegrity** again to stop the operation if file corruption was detected. **/CheckIntegrity** cannot be used with virtual hard disk (VHD) files.

## <span id="Unmounting_an_Image"></span><span id="unmounting_an_image"></span><span id="UNMOUNTING_AN_IMAGE"></span>Unmounting an Image


After you modify a mounted image, you must unmount it. If you mounted your image with the default read/write permissions, you can commit your changes. This makes your modifications a permanent part of the image.

If you modified an applied image, you don't have to do anything else. You'll see any changes you made when you boot the PC.

**To unmount an image**

1.  Open a command prompt or the Deployment Tools Command Prompt with administrator privileges.


2.  Use DISM to unmount the image.

    ```
    Dism /Unmount-image /MountDir:<target_mount_directory> {/Commit | /Discard}
    ```

    where `C:\test\offline` is the location of the mount directory. If you do not specify the parameters to unmount, this option lists all of the mounted images but does not perform the unmount action.

    > [!important]
    > You must use either the **/commit** or **/discard** argument when you use the **/unmount** option.

## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


**If the DISM commands in this topic fail, try the following:**

1.  Make sure that you are using the Windows 10 version of DISM that is installed with the Windows ADK.

2.  Don’t mount images to protected folders, such as your User\\Documents folder.

3.  If DISM processes are interrupted, consider temporarily disconnecting from the network and disabling virus protection.

4.  If DISM processes are interrupted, consider running the commands from the Windows Preinstallation Environment (WinPE) instead.

## <span id="related_topics"></span>Related topics


[DISM Image Management Command-Line Options](dism-image-management-command-line-options-s14.md)

[Service a Windows Image Using DISM](service-a-windows-image-using-dism.md)

 

 






