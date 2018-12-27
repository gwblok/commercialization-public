---

Description: 'Answer files (unattend.xml'
ms.assetid: a29101dc-4922-44ee-a758-d555e6cf39fa
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Answer files (unattend.xml)'

ms.date: 05/02/2017
ms.topic: article


---

# Answer files (unattend.xml)

Answer files (or Unattend files) can be used to modify Windows settings in your images during Setup. You can also create settings that trigger scripts in your images that run after the first user creates their account and picks their default language.

Windows Setup will automatically search for [answer files in certain locations](windows-setup-automation-overview.md#implicit-answer-file-search-order), or you can specify an unattend file to use by using the `/unattend:` option when running Windows Setup (setup.exe).


## <span id="overview"></span><span id="OVERVIEW"></span>Windows settings overview

While you can set many Windows settings in audit mode, some settings can only be set by using an answer file or Windows Configuration Designer, such as adding manufacturer’s support information. A full list of answer file settings (also known as Unattend settings) is in the [Unattended Windows Setup Reference](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/unattend/index).

Enterprises can control other settings by using Group Policy. For more info, see [Group Policy](http://go.microsoft.com/fwlink/p/?linkid=268543).

## <span id="Unattend_overview"></span>Answer file settings

You can specify which configuration pass to add new settings:

-   **1 windowsPE**: These settings are used by the Windows Setup installation program. If you’re modifying existing images, you can usually ignore these settings.

-   **4 specialize**: Most settings should be added here. These settings are triggered both at the beginning of audit mode and at the beginning of OOBE. If you need to make multiple updates or test settings, generalize the device again and add another batch of settings in the Specialize Configuration pass.

-   **6 auditUser**: Runs as soon as you start audit mode.

    This is a great time to run a system test script - we'll add [Microsoft-Windows-Deployment\\RunAsynchronousCommand](https://msdn.microsoft.com/library/windows/hardware/dn915797) as our example. To learn more, see [Add a Custom Script to Windows Setup](add-a-custom-script-to-windows-setup.md).

-   **7 oobeSystem**: Use sparingly. Most of these settings run after the user completes OOBE. The exception is the Microsoft-Windows-Deployment\\Reseal\\[Mode](https://msdn.microsoft.com/library/windows/hardware/dn923110) = Audit setting, which we’ll use to bypass OOBE and boot the PC into audit mode.

    If your script relies on knowing which language the user selects during OOBE, you’d add it to the oobeSystem pass.

-   To learn more, see [Windows Setup Configuration Passes](windows-setup-configuration-passes.md).

> [!Note]
> These settings could be lost if the user resets their PC with the built-in recovery tools. To see how to make sure these settings stay on the device during a reset, see [Sample scripts: Keeping Windows settings through a recovery](windows-deployment-sample-scripts-sxs.md#Keeping_Windows_settings_through_a_recovery).

## <span id="createanswer"></span><span id="CREATEANSWER"></span>Create and modify an answer file

### Step 1: Create a catalog file

1.  Start **Windows System Image Manager**.

2.  Click **File** > **Select Windows Image**.

3.  In **Select a Windows Image**, browse to and select the image file (D:\install.wim). Next, select an edition of Windows, for example, Windows 10 Pro, and click **OK**. Click **Yes** to create the catalog file. Windows SIM creates the file based on the image file, and saves it to the same folder as the image file. This process can take several minutes.

    The catalog file appears in the **Windows Image** pane. Windows SIM lists the configurable components and packages in that image.

    **Troubleshooting:** If Windows SIM does not create the catalog file, try the following steps:

    -   To create a catalog file for either 32-bit or ARM-based devices, use a 32-bit device.

    -   Make sure the Windows base-image file **(\\Sources\\Install.wim**) is in a folder that has read-write privileges, such as a USB flash drive or on your hard drive.

### Step 2: Create an answer file

-   Click **File** > **New Answer File**.

    The new answer file appears in the **Answer File** pane.

    **Note**   If you open an existing answer file, you might be prompted to associate the answer file with the image. Click **Yes**.

### Step 3: Add new answer file settings

1.  Add OEM info:

    In the **Windows Image** pane, expand **Components**, right-click **amd64\_Microsoft-Windows-Shell-Setup\_(version)**, and then select **Add Setting to Pass 4 specialize**.

    In the **Answer File** pane, select **Components\\4 specialize\\amd64\_Microsoft-Windows-Shell-Setup\_neutral\\OEMInformation**.

    In the **OEMInformation Properties** pane, in the **Settings** section, select:
    
    -   Manufacturer=`Fabrikam`
    -   Model=`Notebook Model 1`
    -   Logo=`C:\Fabrikam\Fabrikam.bmp`
        
    Create a 32-bit color with a maximum size of 120x120 pixels, save it as `D:\AnswerFiles\Fabrikam.bmp` file on your local PC, or use the sample from the USB-B key: `D:\ConfigSet\$OEM$\$$\System32\OEM\Fabrikam.bmp`. 
    
    We'll copy the logo into the Windows image in a few steps.

2.  Set the device to automatically [boot to audit mode](https://msdn.microsoft.com/library/windows/hardware/dn923110.aspx):

    In the **Windows Image** pane, expand **Components**, right-click **amd64\_Microsoft-Windows-Deployment\_(version)**, and then select **Add Setting to Pass 7 oobeSystem**.

    In the **Answer File** pane, select **Components\\7 oobeSystem\\amd64\_Microsoft-Windows-Deployment\_neutral\\Reseal**.

    In the **Reseal Properties** pane, in the **Settings** section, select Mode=`Audit`.

3.  Prepare a [script](https://msdn.microsoft.com/library/windows/hardware/dn915797.aspx) to run after Audit mode begins.

    In the **Windows Image** pane, right-click **amd64\_ Microsoft-Windows-Deployment\_(version)** and then click **Add Setting to Pass 6 auditUser**.

    In the **Answer File** pane, expand **Components\\6 auditUser\\amd64\_Microsoft-Windows-Deployment\_neutral\\RunAsynchronous**. Right-click **RunAsynchronousCommand Properties** and click **Insert New AsynchronousCommand**.

    In the **AsynchronousCommand Properties** pane, in the **Settings** section, add the following values:

    `Path = C:\Fabrikam\SampleCommand.cmd`

    `Description = Sample command to run a system diagnostic check.`

    `Order = 1`  (Determines the order that commands are run, starting with 1.)

4.  Add a registry key. In this example, we add keys for the OEM Windows Store program. Use the same process as adding a script, using `CMD /c REG ADD`. 

    For Windows 10 Customer Systems, you may use the OEM Store ID alone or in combination with a Store Content Modifier (SCM) to identify an OEM brand for the OEM Store. By adding a SCM, you can target Customer Systems at a more granular level.  For example, you may choose to target commercial devices separately from consumer devices by inserting unique SCMs for consumer and commercial brands into those devices.

    Add RunAsynchronousCommands for each registry key to add. (Right-click **RunAsynchronousCommand Properties** and click **Insert New AsynchronousCommand**).
    
    ```
    Path = CMD /c REG ADD HKEY_LOCAL_MACHINE\Software\OEM /v Value /t REG_SZ ABCD
    Description = Adds a OEM registry key
    Order = 2
    RequiredUserInput = false
    ```

See the [Unattended Windows Setup Reference](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/unattend/index) for a full list of configuration options. 

**Step 4: Save the answer file**

-   Save the answer file, for example: **D:\\AnswerFiles\\BootToAudit-x64.xml**.

    **Note**   Windows SIM will not allow you to save the answer file into the mounted image folders.
     
**Step 5: Create a script**

Since we specified a script to run in Step 3, let's create that script now.

-   Copy the following sample script into Notepad, and save it as **D:\\AnswerFiles\\SampleCommand.cmd**.

    ```
    @rem Scan the integrity of system files 
    @rem (Required after removing the base English language from an image)
    sfc.exe /scannow

    @rem Check to see if your drivers are digitally signed, and send output to a log file.
    md C:\Fabrikam
    C:\Windows\System32\dxdiag /t C:\Fabrikam\DxDiag-TestLogFiles.txt
    ```

## <span id="Add_the_answer_file_and_script_to_the_image"></span><span id="add_the_answer_file_and_script_to_the_image"></span><span id="ADD_THE_ANSWER_FILE_AND_SCRIPT_TO_THE_IMAGE"></span>Add the answer file and script to the image

### Step 6: Mount an image and add the answer file

1. Use DISM to mount a Windows image. To learn how to mount an image, see [Mount and modify a Windows image using DISM](mount-and-modify-a-windows-image-using-dism.md)

2.  Copy the answer file into the image into the **\\Windows\\Panther** folder, and name it unattend.xml. The Panther folder is one of the folders where Windows searches for an answer file. Create the folder if it doesn’t exist. If there’s an existing answer file, replace it or use Windows System Image Manager to edit/combine settings if necessary.

    ```
    MkDir c:\mount\windows\Windows\Panther
    Copy D:\AnswerFiles\BootToAudit-x64.xml  C:\mount\windows\Windows\Panther\unattend.xml
    MkDir c:\mount\windows\Fabrikam
    Copy D:\AnswerFiles\Fabrikam.bmp    C:\mount\windows\Fabrikam\Fabrikam.bmp
    Copy D:\AnswerFiles\SampleCommand.cmd    C:\mount\windows\Fabrikam\SampleCommand.cmd
    ```
3. Unmount the image, committing the changes. For example:

    ```
    Dism /Unmount-Image /MountDir:"C:\mount\windows" /Commit
    ```

    where *C* is the drive letter of the drive that contains the mounted image.

    This process may take several minutes.

When you [apply your image](apply-images-using-dism.md), Windows will process your unattend file and will configure your settings based on what you specified in the unattend.

