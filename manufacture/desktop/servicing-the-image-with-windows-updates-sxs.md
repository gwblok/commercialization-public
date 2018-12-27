---

Description: 'Add updates to a Windows image'
ms.assetid: 9a8f525c-bb8f-492c-a555-0b512e44bcd1
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Add updates to a Windows image'

ms.date: 05/02/2017
ms.topic: article


---

# Add updates to a Windows image

For many customizations, like adding .inf-style drivers, Windows updates or upgrading the edition, you can mount and edit the Windows image. Mounting an image maps the contents of a file to a temporary location where you can edit the files or use DISM to perform common deployment tasks.

## Notes

-  **Add languages before major updates.** Major updates include hotfixes, general distribution releases, or service packs. If you add a language later, you'll need to re-add the updates.

-  **Add major updates before apps**. These apps include universal Windows apps and desktop applications. If you add an update later, you'll need to re-add the apps.

-  **For major updates, update the recovery image too**: These may include hotfixes, general distribution releases, service packs, or other pre-release updates. We'll show you how to update these later in [Lab 12: Update the recovery image](update-the-recovery-image.md).

-  **If a Servicing Stack Update (SSU) is available, you must install it** before applying the most recent General Distribution Release (GDR) or any future GDRs. See [Windows 10 update history](https://support.microsoft.com/en-us/help/4018124/windows-10-update-history) to see the most recent GDR.


## Add a Windows update package to an image

1.  Get a Windows update package. For example, get the latest cumulative update listed in [Windows 10 update history](https://support.microsoft.com/en-us/help/4464619) from the [Microsoft Update catalog](http://www.catalog.update.microsoft.com). If the update has any prerequisite updates, get those too.

    To learn more, see [https://myoem.microsoft.com/oem/myoem/en/product/winemb/pages/comm-ms-updt-ctlg-trnstn.aspx](https://myoem.microsoft.com/oem/myoem/en/product/winemb/pages/comm-ms-updt-ctlg-trnstn.aspx).    

2.  Add the updates to a [mounted](mount-and-modify-a-windows-image-using-dism.md) or online image. For packages with dependencies, either install the packages in order, or add them all at once using a single DISM command.

    **Example**: adding a cumulative update to a mounted image:

    ```
    Dism /Add-Package /Image:"C:\mount\windows" /PackagePath="windows10.0-kb4456655-x64_fca3f0c885da48efc6f9699b0c1eaf424e779434.msu"  /LogPath=C:\mount\dism.log
    ```

    **Example**: adding multiple updates:

    ```
    Dism /Add-Package /Image:"C:\mount\windows" /PackagePath="C:\WindowsUpdates\windows10.0-kb00001-x64.msu" /PackagePath="C:\WindowsUpdates\windows10.0-kb00002-x64.msu" /PackagePath="C:\WindowsUpdates\windows10.0-kb00003-x64.msu" /LogPath=C:\mount\dism.log
    ```

3.  Verify that the packages appear correctly:

    ```
    Dism /Get-Packages /image:<path_to_image>
    ```

    Review the resulting list of packages and verify that the list contains the package. For example:

    ```
    Package Identity : Package_for_RollupFix~31bf3856ad364e35~amd64~~15063.250.1.1
    State : Installed
    Release Type : Security Update
    Install Time : 04/29/2017 6:26 PM

    The operation completed successfully.
    ```    

    > [!Note]
    > Each package will usually be a new KB, and will increase the build revision number of Windows on the device. The revision number of windows a device can be found in the following registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\UBR`.

5. If you're done updating your image, you can unmount it, committing changes.
