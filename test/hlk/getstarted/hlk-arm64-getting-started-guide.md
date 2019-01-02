---
title: HLK ARM64 Getting Started Guide
description: HLK ARM64 Getting Started Guide
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 57E7C933-FD93-4254-A65A-DA47D2BFE4C6


ms.date: 10/15/2017
ms.topic: article


---

# HLK ARM64 Getting Started Guide


Setup and testing for ARM64 desktop machines largely follows the guidelines found in the [HLK Getting Started Guide](windows-hlk-getting-started.md). Instructions specific to ARM64 are described in this topic.

This topic provides a basic introduction to using the Windows Hardware Lab Kit (HLK). Once you are familiar with the tools and process, you can review the [HLK User's Guide](../user/windows-hardware-lab-kit-user-s-guide.md) for additional information.

## <span id="Windows_HLK_Prerequisites"></span><span id="windows_hlk_prerequisites"></span><span id="WINDOWS_HLK_PREREQUISITES"></span>Windows HLK Prerequisites


Prerequisites are the same for all desktop machines. See the [HLK Prerequisites](windows-hlk-prerequisites.md) topic for more information.

## <span id="Step_1__Install_Controller_and_Studio_on_the_test_server"></span><span id="step_1__install_controller_and_studio_on_the_test_server"></span><span id="STEP_1__INSTALL_CONTROLLER_AND_STUDIO_ON_THE_TEST_SERVER"></span>Step 1: Install Controller and Studio on the test server


Test server setup is the same for all desktop testing. See [Step 1: Install Controller and Studio on the test server](step-1-install-controller-and-studio-on-the-test-server.md) for more information.

## <span id="step-2"></span><span id="STEP-2"></span>Step 2: Install Client on the test system(s)

After you install the HLK on the test server, you are ready to add test systems to the environment. You must install the HLK Client software on each test system. The HLK Client software is stored on the Windows HLK test server.

Testing for ARM64 Desktop requires the client systems to be set up differently than testing for x86/x64. ARM64 Desktop testing uses a different setup path. Also, a complete submission package requires testing to be done in two modes -- native ARM64 and x86 on ARM64. Testing can be done with multiple machines or a single machine, but using a single machine requires the HLK client to be uninstalled and reinstalled using the directions below to change the modes. 

Depending on the scenario, it may be required that testing be done in native ARM64 mode, x86 on ARM64, or a combination of the two. The scenarios below will outline which mode(s) are required for testing.

Testing can be done with multiple machines or a single machine, but using a single machine requires the HLK client to be uninstalled and reinstalled using the directions below to change the modes. 


### <span id="Scenarios"></span><span id="scenarios"></span><span id="SCENARIOS"></span>Scenarios

| Scenario     | Mode                         |
|--------------|------------------------------|
| Audio Device | Native                       |
| Wireless Lan | Native and x86 on ARM64 mode |
| System       | Native and x86 on ARM64 mode |

 

>[!NOTE]
> The mode required may change with new releases of the kit.

 

Once the mode for testing is identified the following instructions will walk you through client setup.

> [!WARNING]
>  If you are testing software, be sure to install the product on the test system first, and then install the HLK Client software.

> [!NOTE]
> It is recommended that the client system is on A/C (plugged in) and that the Power Options are set to **Never** for **Put the computer to sleep** settings.

 

### <span id="To_install_the_Windows_HLK_Client"></span><span id="to_install_the_windows_hlk_client"></span><span id="TO_INSTALL_THE_WINDOWS_HLK_CLIENT"></span>To install the Windows HLK Client

1.  **Run client setup**

    For x86/x64 client systems, on the test system, run the following:

    ``` syntax
    \\<ControllerName>\HLKInstall\Client\Setup.cmd
    ```

    For ARM64 Desktop client systems, there are two different install paths depending on the mode the client is being set up to test in. 

    >[!NOTE]
    >Because of the dual-mode nature of ARM64, a best practice is to use two (2) clients, one in native mode and one in emulated mode per the instructions below.
    
    **Native Mode:**
    
    On the test system, run the following:
    
    ``` syntax
    \\<controllername>\HLKInstall\CoreSystemClient\InstallWTTClient
    ```
    
    **x86 on ARM64 Mode:**
    
    On the test system, start a command prompt with administrator privileges, and run the following:
    
    ``` syntax
    \\<controllername>\HLKInstall\CoreSystemClient\InstallWTTClient UseEmulationForTestContent
    ```

    (Replace &lt;ControllerName&gt; with the name of the test server.)

2.  The Windows Hardware Lab Kit Client Setup wizard appears. To start the wizard, choose **Next**.
3.  On the Internet Connection Firewall Agreement page, select **Yes I will allow a port to be opened**, and then choose **Next**.
    >[!NOTE]
    >If the Internet Connection Firewall Agreement page doesn't appear, either Windows Firewall isn't installed, or another software firewall or hardware firewall is installed on the computer. If another firewall is installed, you must manually open TCP port 1771 to proceed with installation. Refer to the instructions that came with your firewall product to manually open a TCP port. If you continue without opening port 1771, the installation may fail or the Client software might not function properly.

     

4.  When the **Ready to Install** page appears, select **Install**.
5.  Click **Finish** to exit the wizard.
    >[!TIP]
    >When installation completes, confirm its success by going to the Control Panel and choosing Uninstall a program. Windows Hardware Lab Kit Client should appear in the program list.

     

6.  Repeat steps 1-5 for each test system.

## <span id="Step_3__Create_a_machine_pool"></span><span id="step_3__create_a_machine_pool"></span><span id="STEP_3__CREATE_A_MACHINE_POOL"></span>Step 3: Create a machine pool


Machine pool creation is the same for all desktop testing. See [Step 3: Create a machine pool](step-3-create-a-machine-pool.md) for more information.

## <span id="Step_4__Create_a_project"></span><span id="step_4__create_a_project"></span><span id="STEP_4__CREATE_A_PROJECT"></span>Step 4: Create a project


x86/x64 instructions: [Step 4: Create a project](step-4-create-a-project.md)

After you setup your test server and clients, you're ready to create a project. A project defines what you want to test. The most common project corresponds to the device you want to submit for certification.

You can create large projects that represent a wide range of scenarios. You can also create several smaller projects and merge the results into one package.

>[!NOTE]
> For ARM64 Desktop testing, multiple projects are required to form a complete submission package (one for each mode). When testing is complete for each mode, create hlkx packages and then merge the packages together to make a single package for submission. 

 

In the remaining examples, you create a project for a device and run all associated certification tests. Then, you create a single package for submission that contains all of the passing test results.

The following image shows the Studio **Project** tab.

![](images/hlk-studio-project-tab.png)

### <span id="Creating_a_project"></span><span id="creating_a_project"></span><span id="CREATING_A_PROJECT"></span>Creating a project

1.  In Windows HLK Studio, choose the **Project** tab, and then choose **Create project**.
2.  Replace the default project name with the name of your project, and then press Enter.
    >[!NOTE]
    > A project should have a meaningful name that indicates its contents, for example, **Fabrikam Multi-function Device Model Z**.

     

When the project name appears on the page, the project is created.

The right pane displays project details. More information is displayed here once you start testing your device. You can check the status of any project by loading it and referring to this pane.

## <span id="Step_5__Select_target_to_test"></span><span id="step_5__select_target_to_test"></span><span id="STEP_5__SELECT_TARGET_TO_TEST"></span>Step 5: Select target to test


Selecting targets is the same for all desktop testing. See [Step 5: Select target to test](step-5--select-target-to-test.md) for more information.

## <span id="Step_6__Select_and_run_tests"></span><span id="step_6__select_and_run_tests"></span><span id="STEP_6__SELECT_AND_RUN_TESTS"></span>Step 6: Select and run tests


The **Tests** tab displays all of the tests that are associated with the features found on your device. In the HLK, test categories replace the level classifications previously used with the HCK. The HLK can be used throughout the product life cycle to test and measure quality at each stage of development. You can filter and sort the listed tests in the following ways:

-   Test Phase Categorization
    -   Bring Up
    -   Development and Integration
    -   Reliability
    -   Tuning and Validation
    -   Manufacturing
    -   Support
-   Status
-   Test Name
-   Type (manual, non-distributed, special configuration, multiple machine)
-   Length
-   Target
-   Machine(s)

>[!NOTE]
> - You can hover over the test type icons with your mouse for more information about the test types.
> -  Manual tests that require user input can interrupt the test process. We recommend that you run manual tests separately from automated tests.
> -  Some tests require additional input before running. Windows HLK Studio prompts you for more info as needed.

 

The following image shows the Studio **Tests** tab.

![](images/hlk-studio-tests-tab.png)

### <span id="Playlists"></span><span id="playlists"></span><span id="PLAYLISTS"></span>Playlists

Playlists are collections of tests that you can use to define various scenarios in which to test your device. The Windows Hardware Compatibility Program uses an official playlist to determine which devices meet the requirements for compatibility with Windows 10.

You can load a playlist by choosing **Load Playlist** from within the **Tests** tab. You can load only one playlist at a time. To choose a different playlist, you must first unload the current playlist by choosing **Unload Playlist** from the **Tests** tab.

The following image shows the **Load Playlist File** dialog.

![](images/hlk-studio-load-playlist-file-dialog.png)

Once a playlist is loaded, only tests that are applicable to each target are shown in the UI.

Test results against all playlists for a specific target are kept until the target is removed from the project. When a playlist is loaded, any previous test results against that playlist are also loaded.

You can save an existing collection of tests as a playlist by choosing Save Selected as Playlist.

>[!IMPORTANT]
>When using an official playlist, you must use the version of the playlist that matches the version of the kit you are using. For example, if using version 1607 of the HLK, you must also use version 1607 of the playlist.

 

>[!NOTE]
> ARM64 Desktop testing: There are two playlists, one for tests that run in **Native mode** and one for tests that run in **x86 on ARM64** mode. Ensure that the appropriate playlist is being applied to the project that has the HLK client installation which matches the mode intended for testing.

 

### <span id="Running_a_test"></span><span id="running_a_test"></span><span id="RUNNING_A_TEST"></span>Running a test

If using a playlist, be sure to load it before proceeding.

1.  Filter the test results by using the **View By** dropdown list.
2.  Check the box next to each test that you want to run.
3.  Run the selected tests by choosing **Run Selected**.

If any additional input is needed, Windows HLK Studio will prompt you.

A progress bar appears. A slight delay occurs when you run a test.

>[!NOTE]
> To learn more about any test, select the test from the list, and press F1 key, or right-click, and select **Test Description**. To cancel any running test, right-click it and select **Cancel**.

 

As tests complete, the results are displayed in the Status column. A green checkmark means that it passed, while a red X means that it failed. The pane on the right displays project summary information, including target(s) selected, operating systems being tested, product types you qualify for, and status of all tests.

To learn more about the different options on this page, see [HLK Studio - Tests Tab](../user/hlk-studio---tests-tab.md).

## <span id="Step_7__View_test_results_and_log_files"></span><span id="step_7__view_test_results_and_log_files"></span><span id="STEP_7__VIEW_TEST_RESULTS_AND_LOG_FILES"></span>Step 7: View test results and log files


x86/x64 instructions: [Step 7: View test results and log files](step-7-view-test-results-and-log-files.md)

>[!NOTE]
>  Due to ARM64 Desktop having scenarios that involve multiple projects, it will be required that these projects be merged to have a complete HLK package for submission. For information on merging packages, see [Merge packages](../user/merge-packages.md).

 

## <span id="Step_8__Create_a_submission_package"></span><span id="step_8__create_a_submission_package"></span><span id="STEP_8__CREATE_A_SUBMISSION_PACKAGE"></span>Step 8: Create a submission package


Once any merging is complete, submitting packages is the same for all desktop machines. See [Step 8: Create a submission package](step-8-create-a-submission-package.md) topic for more information.




