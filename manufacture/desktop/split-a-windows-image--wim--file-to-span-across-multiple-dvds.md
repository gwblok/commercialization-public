---
Description: 'Split a Windows image file (.wim) to span across multiple DVDs'
ms.assetid: 3861fd65-4c2b-4955-a0af-233e0bbce454
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Split a Windows image file (.wim) to span across multiple DVDs'

ms.date: 01/31/2018
ms.topic: article


---

# Split a Windows image file (.wim) to span across multiple DVDs


Split a Windows image (.wim) file into a set of smaller (.swm) files.

Use this procedure when you're installing Windows from media that can't handle the Windows image file size, for example:

-  **DVDs**  (A standard single-sided DVD stores 4.7GB).

-  **USB keys formatted as FAT32**. FAT32 is required to boot many modern (UEFI-based) PCs, but has a maximum file size of 4GB.
   (Workaround: [Create a USB key with multiple partitions](winpe--use-a-single-usb-key-for-winpe-and-a-wim-file---wim.md).)

## Limitations:
* You can’t modify a set of split image (.swm) files.
* Applying split image (.swm) files is only supported when all of the .swm files are in the same folder. This means for DVD deployment, you'll need to copy the files over to the destination PC before you can use Windows Setup or DISM /Apply-Image, as shown in this topic.

## Split the file

1.  Mount your Windows distribution ISO.

2.  Split the Windows image:

    ```
    Dism /Split-Image /ImageFile:C:\sources\install.wim /SWMFile:C:\sources\install.swm /FileSize:4700
    ```

    where:

    -   `C:\sources\install.wim` is the name and the location of the image file that you want to split.

    -   `C:\sources\install.swm` is the destination name and the location for the split .swm files. The first split .swm file is named install.swm file. The file names for the next files include numbers, for example, install2.swm file, install3.swm file, and so on.

    -   `4700` is the maximum size in MB for each of the split .swm files to be created.

## USB deployment

Store all of the .swm files in the same folder on the USB key. 

For Windows Setup instructions, see the Troubleshooting section from [Install Windows from a USB flash drive](install-windows-from-a-usb-flash-drive.md).

## DVD deployment

1.  Copy the files to individual DVDs. For example, insert the first DVD and type:
    ```
    copy C:\images\install.swm D:\*
    ```

    Then insert the second DVD and type:
    ```
    copy C:\images\install2.swm D:\*
    ```

    And so on until all .swm files are copied to DVDs.

2.  [Boot your destination PC to Windows PE from DVD](winpe-create-a-boot-cd-dvd-iso-or-vhd.md).

    From Windows PE, you can either deploy using Windows Setup or a script.

3.  Configure and format your hard drive partitions, as shown in [Capture and Apply Windows, System, and Recovery Partitions](capture-and-apply-windows-system-and-recovery-partitions.md).

4.  Copy the files to a single temporary folder. For example, insert the first DVD and type:
    ```
    md C:\TempInstallFolder
    copy d:\install.swm c:\TempInstallFolder\*
    ```

    Then insert the second DVD and type:
    ```
    copy d:\install2.swm c:\TempInstallFolder\*
    ```

    And so on until all .swm files are copied.

5.  Install using Windows Setup or a script.

    *  **Windows Setup**: Insert a DVD with Windows Setup, and use it to install the split Windows image files.
       ```
       D:\Setup.exe /InstallFrom:"C:\TempInstallFolder\install.swm"
       ```

    * **Use a script**

      1.  Apply your image using the DISM /Apply-Image /SWMFile option:
          ```
          Dism /Apply-Image /ImageFile:C:\TempInstallFolder\install.swm /SWMFile:c:\TempInstallFolder\install*.swm /Index:1 /ApplyDir:D:\
          ```

      2.  Set up your system and recovery partitions, as shown in [Deploy Windows using a Script](deploy-windows-with-a-script-sxs.md).

6. Clean up: remove the temporary folder
   ```
   rd c:\TempInstallFolder /s /q
   ```


## <span id="related_topics"></span>Related topics

[Capture and Apply Windows, System, and Recovery Partitions](capture-and-apply-windows-system-and-recovery-partitions.md)

[WinPE: Use a single USB key for WinPE and a WIM file (.wim)](winpe--use-a-single-usb-key-for-winpe-and-a-wim-file---wim.md)

[Install Windows from a USB flash drive](install-windows-from-a-usb-flash-drive.md)

[DISM Image Management Command-Line Options](dism-image-management-command-line-options-s14.md)
