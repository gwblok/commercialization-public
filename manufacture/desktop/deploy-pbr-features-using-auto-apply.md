---

Description: 'Push-button reset features are included with Windows 10 for desktop editions (Home, Pro, Enterprise, and Education), though you''ll need to perform additional steps to deploy PCs with the following customizations.'
title: 'Deploy push-button reset features with auto-apply folders'

ms.date: 10/02/2018
ms.topic: article
ms.custom: RS5
---

# Deploy push-button reset features using Auto-apply folders

Push-button reset features are included with Windows 10 for desktop editions (Home, Pro, Enterprise, and Education), though you'll need to perform additional steps to deploy PCs with the following customizations.

-   Windows desktop applications
-   Windows settings, such as customized OOBE screens or Start Menus.
-   Customized partition layouts.

These steps also show you how to add your own scripts during a reset to capture logs or perform other cleanup tasks.

## <span id="Prerequisites"></span><span id="prerequisites"></span><span id="PREREQUISITES"></span>Prerequisites


To complete these procedures, you'll need a technician PC which has Windows 10 and the following Windows Assessment and Deployment Kit (ADK) for Windows 10 components installed. Note that starting with Windows 10, version 1809, WinPE is an addon to the ADK, and isn't included in the ADK installer:

-   Deployment Tools
-   Imaging and Configuration Designer (ICD)
-   User State Migration Tool (USMT)
-   Windows Preinstallation Environment (Windows PE)

You'll also need:

-   A destination PC with drive size of 100 GB or larger
-   A Windows 10 for desktop editions image (install.wim)
-   A Windows RE boot image (Winre.wim) (You'll extract this from a Windows 10 image).

For an overview of the entire deployment process, see the [Desktop manufacturing guide](http://go.microsoft.com/fwlink/p/?LinkId=526101).

Use the follow steps to prepare the ScanState tool to capture Windows desktop applications after they have been installed:

## Step 1: Prepare the ScanState tool

1.  On the technician PC, copy the Windows ADK files from Windows User State Migration Tool (USMT) and Windows Setup to a working folder. You'll need to match the architecture of the destination device. You don't need to copy the subfolders.

    ```cmd
    md C:\ScanState_amd64
    xcopy /E "C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\User State Migration Tool\amd64" C:\ScanState_amd64
    xcopy /E /Y "C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Windows Setup\amd64\Sources" C:\ScanState_amd64
    ```

2.  Copy the contents of the working folder to a network location or USB flash drive.

Use the following steps to customize your Windows RE boot image if additional drivers and language packs are needed.

## Step 2: Extract and customize the Windows RE boot image (optional)

1.  On the technician PC, click **Start**, and type deployment. Right-click **Deployment and Imaging Tools Environment** and then select **Run as administrator**.
2.  In **Deployment and Imaging Tools Environment**, create the folder structure to store the Windows image and its mount point.

    ```cmd
    Mkdir C:\OS_image\mount
    ```

3.  Create the folder structure to store the Windows RE boot image and its mount point.

    ```cmd
    Mkdir C:\winre_amd64\mount
    ```

4.  Mount the Windows image (install.wim) to the folder \\OS\_image\\mount by using DISM.

    ```cmd
    Dism /mount-image /imagefile:C:\OS_image\install.wim /index:1 /mountdir:C:\OS_image\mount
    ```

    where `Index:1` is the index of the selected image in the Install.wim file.

5.  Copy the Windows RE image from the mounted Windows image to the new folder.

    ```cmd
    xcopy /H C:\OS_image\mount\windows\system32\recovery\winre.wim C:\winre_amd64 
    ```

6.  Unmount the Windows image. Tip: If you haven't made any other changes in the Windows image, you can unmount the image faster by using the `/discard` option.

    ```cmd
    Dism /unmount-image /mountdir:C:\OS_image\mount /discard
    ```

7.  Mount the Windows RE boot image for editing.

    ```cmd
    Dism /mount-image /imagefile:C:\winre_amd64\winre.wim /index:1 /mountdir:C:\winre_amd64\mount
    ```

    where `Index:1` is the number of the selected image in the Winre.wim file.

    Once the Winre.wim file is extracted from the Install.wim file, you can customize the Windows RE boot image.

8.  Add language packs, boot-critical device drivers, and input device drivers to the Windows RE boot image. To learn more, see [Customize Windows RE](customize-windows-re.md).
9.  Commit your customizations and unmount the image.

    ```cmd
    Dism /unmount-image /mountdir:C:\winre_amd64\mount /commit 
    ```

If you are planning to customize only the settings common to all editions of Windows 10 (including Windows 10 Mobile), use the following steps to create a provisioning package which specifies settings to be restored during recovery:

## Step 3: Create a provisioning package with settings to be restored (optional)

1.  On the technician PC, start Windows Imaging and Configuration Designer (ICD).
2.  Click **File** &gt; **New Project**.
3.  Enter a project name and description, and then click **Next**
4.  In the **Select project workflow** step, select the **Provisioning Package** option, and then click **Next**.
5.  In the **Choose which settings to view and configure** step, select the **Common to all Windows editions** option, and then click **Next**.
6.  In the **Import a provisioning package (optional)** step, click **Finish** to create the new project.
7.  Use the **Available customizations** pane to add settings and specify the defaults which should be restored during recovery. The settings will appear in the **Selected customizations** pane.
8.  Click **Export** &gt; **Provisioning package**.
9.  In the **Describe the provisioning package** step, click **Next**.
10. In the **Select the security details for the provisioning package** step, click **Next**.
11. In the **Select where to save the provisioning package** step, enter a location to save the package (such as a network share) and then click **Next**.
12. Click **Build** to create the provisioning package.
13. After the provisioning package is created, click **Finish**.

If your customizations include settings specific to editions of Windows 10 for desktop editions, use the following steps to create an unattend.xml which specifies the settings to be restored during recovery:


## Step 4: Copy configuration files and related asset files into Auto-apply folders

Auto-apply folders are new in Windows 10, version 1809. These folders make it easier for you to restore common settings, including unattend, OOBE, and taskbar layout during PBR. You can use Auto-apply folders or extensibility points, but not both. If Auto-apply folders and extensibility points are configured, Windows will use the extensibility points.

1.  Create a folder in your Windows image called `C:\Recovery\AutoApply`

    ```cmd
    MkDir C:\Recovery\AutoApply
    ```

2. Copy configuration files and the related asset files

    - Copy the unattend.xml file you want for recovery to `C:\Recovery\AutoApply\` and any asset files to `C:\Recovery\AutoApply\CustomizationFiles`. ()
    - Copy your LayoutModification.xml to `C:\Recovery\AutoApply\` and any asset files to `C:\Recovery\AutoApply\CustomizationFiles`
    - Copy your TaskbarLayoutModification.xml to `C:\Recovery\AutoApply\` and any asset files to `C:\Recovery\AutoApply\CustomizationFiles`
    - Copy `%windir%\System32\OOBE\info` and all its contents to `C:\Recovery\AutoApply\OOBE`
    
## Step 5: Deploy and customize Windows

1.  On the destination PC, boot to Windows PE.
2.  At the Windows PE command prompt, run the script to create the recommended hard drive partitions.

    ```
    Diskpart /s N:\CreatePartitions.txt
    ```

    where N:\\CreatePartition is the location of the file.

3.  Apply the Windows reference image to the Windows partition.

    ```
    Dism /Apply-Image /ImageFile:N:\Install.wim /Index:1 /ApplyDir:W:\
    ```

    Optional: You can also specify the /compact option so that the files written to disk are compressed. For example:

    ```
    Dism /Apply-Image /ImageFile:N:\Install.wim /Index:1 /ApplyDir:W:\ /Compact:on
    ```

    This is useful if you are deploying Windows onto PCs with limited storage capacity, but is not recommended on PCs with rotational storage devices.

4.  Configure the system partition by using BCDboot.

    ```
    W:\Windows\System32\Bcdboot W:\Windows
    ```

5.  Create a folder in the Windows RE tools partition, and copy your custom Windows RE boot image to it.

    ```
    Mkdir T:\Recovery\WindowsRE
    xcopy /H N:\Winre.wim T:\Recovery\WindowsRE
    ```

    where T:\\ is the Windows RE tools partition.

    > [!important]
    > You must store Winre.wim in \\Recovery\\WindowsRE.

     

6.  Register the Windows RE boot image together with the Windows image.

    ```
    W:\Windows\System32\Reagentc /setreimage /path T:\Recovery\WindowsRE /target W:\Windows
    ```

7.  Use Diskpart to conceal the Windows RE tools (T:\\) partition from Windows Explorer.

    **For UEFI-based PCs:**

    ```cmd
    select disk 0
    select partition 4
    remove
    set id=de94bba4-06d1-4d40-a16a-bfd50179d6ac
    gpt attributes=0x8000000000000001
    exit
    ```

    **For BIOS-based PCs:**

    ```cmd
    select disk 0
    select partition 3
    remove
    set id=27
    exit
    ```

8.  Customize the Windows image on the destination PC:
    1.  Perform offline customizations to the Windows image, such as installing INF-based driver packages specific to the destination PC, installing OS updates and language packs, or provisioning additional Windows apps.
    2.  Boot the destination PC to audit mode. This can be accomplished by using an answer file with the Microsoft-Windows-Deployment | Reseal | Mode = audit setting, or by first booting the PC to OOBE, and then pressing CTRL+SHIFT+F3.
    3.  Perform any remaining customizations such as installing applications and device software packages that are specific to the destination PC.

9.  If you have installed OS updates, clean up the superseded components and mark the updates as permanent so that they will be restored during recovery:

    ```cmd
    DISM.exe /Cleanup-Image /StartComponentCleanup
    ```

## Step 6: Capture and deploy customizations for recovery

1.  Use the ScanState tool to capture the installed customizations into a provisioning package. Use the /config option to specify one of the default configuration files included with the ADK, and save the .ppkg file in the folder C:\\Recovery\\Customizations.

    ```cmd
    N:\ScanState_amd64\scanstate.exe /apps /config:<path_to_config_file> /ppkg C:\Recovery\Customizations\apps.ppkg /o /c /v:13 /l:C:\ScanState.log
    ```

    where N:\\ is the location of the ScanState tool installed in Step 1.

2.  If you have used Windows ICD to create additional provisioning packages with customizations which should be restored during recovery, copy the packages to the destination PC. For example:

    ```cmd
    xcopy N:\RecoveryPPKG\*.ppkg C:\Recovery\Customizations
    ```

    where N:\\ is the location where the additional provisioning packages are located.

3.  Copy any Push-button reset configuration file (resetconfig.xml) and related scripts to the destination PC, and then configure permissions to write/modify them. For example:

    ```cmd
    mkdir C:\Recovery\OEM
    ```

    where N:\\ is the location where the configuration file and scripts are located.

4.  Restrict the Write/Modify permissions of the customizations, and hide the root folder. For example:

    ```cmd
    icacls C:\Recovery\Customizations /inheritance:r /T
    icacls C:\Recovery\Customizations /grant:r SYSTEM:(F) /T
    icacls C:\Recovery\Customizations / grant:r *S-1-5-32-544:(F) /T
    icacls C:\Recovery\OEM /inheritance:r /T
    icacls C:\Recovery\OEM /grant:r SYSTEM:(F) /T
    icacls C:\Recovery\OEM / grant:r *S-1-5-32-544:(F) /T
    attrib +H C:\Recovery
    ```

5.  Use the Sysprep tool to reseal the Windows image without using the /generalize option.

    ```cmd
    Sysprep /oobe /exit
    ```

    **Note**  Important: You must configure the image that you are shipping to the customer to boot to OOBE.

     

6.  (Optional) To save space, you can also convert your installed Windows desktop applications into file pointers referencing the customizations package. To do so, boot the destination PC to Windows PE and run the following:

    ```cmd
    DISM /Apply-CustomDataImage /CustomDataImage:C:\Recovery\Customizations\USMT.ppkg /ImagePath:C:\ /SingleInstance
    ```

7.  Shut down the destination PC for packaging and shipment. When the user starts the PC for the first time, it will boot to OOBE.

## Step 7: Verify your customizations

1.  Verify that your customizations are restored after recovery, and that they continue to function by running the Refresh your PC and Reset your PC features from the following entry points:

    **Settings :** From the Start Menu, click **Settings &gt; Update & security &gt; Recovery**. Click the **Get Started** button under **Reset this PC** and follow the on-screen instructions.

    **Windows RE**: From the Choose an option screen in Windows RE, click **Troubleshoot &gt; Reset this PC** and then follow the on-screen instructions

2.  **Verify that recovery media can be created, and verify its functionality by running the bare metal recovery feature:**

    1.  Launch Create a recovery drive from Control Panel.
    2.  Follow the on-screen instructions to create the USB recovery drive.
    3.  Boot the PC from the USB recovery drive
    4.  From the Choose an option screen, click **Troubleshoot**
    5.  Click **Recover from a drive** and then follow the on-screen instructions

    **Note**  The Push-button reset UI has been redesigned in Windows 10. The **Keep my files** option in the UI now corresponds to the **Refresh your PC** feature, whereas the **Remove everything** option corresponds to the **Reset your PC** feature.

     

## <span id="related_topics"></span>Related topics


[ScanState Syntax](http://go.microsoft.com/fwlink/p/?linkid=615076)

[Bare metal reset/recovery: Create recovery media while deploying new devices](create-media-to-run-push-button-reset-features-s14.md)

[Deploy push-button reset features using ScanState](http://go.microsoft.com/fwlink/?LinkId=615126)
