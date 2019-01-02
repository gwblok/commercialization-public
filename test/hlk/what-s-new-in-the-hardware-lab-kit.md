---
title: What's new in the Hardware Lab Kit
description: What's new in the Hardware Lab Kit
MS-HAID:
- 'p\_hlk.what\_s\_new\_in\_the\_hardware\_lab\_kit'
- 'wdknodes.what\_s\_new\_in\_the\_hardware\_lab\_kit'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
Search.SourceType: Video
ms.assetid: 8A9F73C6-030F-4A1D-A466-6A9ADDD06A51


ms.date: 10/15/2017
ms.topic: article


---

# What's new in the Hardware Lab Kit


## <span id="What_s_new_in_this_release"></span><span id="what_s_new_in_this_release"></span><span id="WHAT_S_NEW_IN_THIS_RELEASE"></span>**What's new in this release**


### <span id="Breaking_changes"></span><span id="breaking_changes"></span><span id="BREAKING_CHANGES"></span>Breaking changes

>[!NOTE]
>With each new release, anyone who builds tools that utilize the HLK object model should rebuild those tools to use the latest versions of the object model files. In addition, be sure to always use the same version of each object model file (i.e. do not mix object model files from different kit releases).

### Virtual Hardware Lab Kit (VHLK)
New for 1809! The Microsoft Virtual Hardware Lab Kit (VHLK) is the entire Hardware Lab Kit pre-installed and pre-configured on a VHDX, ready to boot. Use the VHLK to save setup time, quickly stand up a controller, and run Windows Hardware Certification from a virtual machine. For more details, check out the [VHLK Getting Started Guide](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/getstarted/getstarted-vhlk).
- Ready to boot and use
- Run the HLK Controller as a virtual machine
- Host the HLK Controller virtual machine on developer machines instead of dedicated Controller hardware

### <span id="Server_support"></span><span id="server_support"></span><span id="SERVER_SUPPORT"></span>Server support

|**HLK version**|**Compatable server OS versions**| 
|--- |--- | 
|1809|Windows Server 2012, Windows Server 2012 R2, Windows Server 2016|
|1803|Windows Server 2012, Windows Server 2012 R2, Windows Server 2016| 
|1709|Windows Server 2012, Windows Server 2012 R2, Windows Server 2016| 
|1703|Windows Server 2012, Windows Server 2012 R2, Windows Server 2016| 
|1607|Windows Server 2008 R2 SP1, Windows Server 2012, Windows Server 2012 R2, Windows Server 2016| 

>[!NOTE]
>Windows Server 2019 is not supported as a host OS for the 1809 HLK Controller. However, it is supported as a client OS. 

### Updated test content
Test content updated for better coverage for 1809 testing, across various architectures.

## **Known issues this release**

### HLK install fails with a database-related error
This error can occur when uninstalling and then reinstalling HLK. When the new instance of HLK is installed, one of the following error messages appears when installing and rolls back
- There is already an object named DSLinkType in the database. 
- The database database_name already exists. 
- Failed to create SQL database. 

When uninstalling HLK, database uninstall can fail if the database is locked by another process. The HLK uninstall reports success, but the database is left behind.
To recover, follow these steps:
1. From an elevated command prompt, run ```SQLCMD -E``` 
2. From the SQL Shell command line, enter the following:
3. ```ALTER DATABASE WTTIdentity SET SINGLE_USER WITH ROLLBACK IMMEDIATE```
4. ```DROP DATABASE WTTIdentity```
5. ```GO```
6. ```ALTER DATABASE HLKJobs SET SINGLE_USER WITH ROLLBACK IMMEDIATE```
7. ```DROP DATABASE HLKJobs```
8. ```GO```
9. Verify that ```C:\Program Files\Microsoft SQL Server\MSSQL(sql version).MSSQLSERVER\MSSQL\DATA``` contains no files starting with WTTIdentity or HLKJobs
10. Install the HLK 

### HLK does not update existing SQL database with latest security fix
If your existing SQL Server database is unpatched, installing the HLK will not update the database with the latest security fixes. 
 
To patch SQL Server: 
Option 1: Uninstall SQL Server before installing the HLK. The HLK will install SQL Server and the most recent hotfix as of RTM. At this point, you may use Windows Update to keep your SQL Server instance updated.
Option 2: Manually patch your existing SQL Server before HLK install. 

## <span id="What_s_new_in_previous_releases"></span><span id="what_s_new_in_previous_releases"></span><span id="WHAT_S_NEW_IN_PREVIOUS_RELEASES"></span>**What's new in previous releases**

### <span id="Improved_playlist_support"></span><span id="improved_playlist_support"></span><span id="IMPROVED_PLAYLIST_SUPPORT"></span>Improved playlist support

The process for loading and using playlists has been improved and simplified. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/test/hlk/getstarted/step-6-select-and-run-tests">Step 6: Select and run tests</a> in the Getting Started guide

### <span id="Support_for_ARM64_desktop"></span><span id="support_for_arm64_desktop"></span><span id="SUPPORT_FOR_ARM64_DESKTOP"></span>Support for ARM64 desktop

HLK tests can now target ARM64 desktop machines.

### <span id="Nano_Server_testing"></span><span id="nano_server_testing"></span><span id="NANO_SERVER_TESTING"></span>Nano Server testing

HLK now includes tests for Nano Server.

### <span id="Improved_diagnosability_of_failed_HLK_tests"></span><span id="improved_diagnosability_of_failed_hlk_tests"></span><span id="IMPROVED_DIAGNOSABILITY_OF_FAILED_HLK_TESTS"></span>Improved diagnosability of failed HLK tests

The Results tab now indicates when a test fails due to a system crash. The tab also shows information from the associated Bug Check along with a link to help documentation for further information.

See the following topics for more information:

-   <a href"https://docs.microsoft.com/en-us/windows-hardware/test/hlk/getstarted/step-7-view-test-results-and-log-files">Step 7: View test results and log files (Getting started guide)</a>
-   <a href"https://docs.microsoft.com/en-us/windows-hardware/test/hlk/user/hlk-studio---results-tab">HLK Studio - Results Tab</a>
-   <a href"https://docs.microsoft.com/en-us/windows-hardware/test/hlk/user/troubleshooting-windows-hlk-test-failures">Troubleshooting Windows HLK Test Failures (system crashes)</a>

### <span id="Exporting_failed_HLK_jobs"></span><span id="exporting_failed_hlk_jobs"></span><span id="EXPORTING_FAILED_HLK_JOBS"></span>Exporting failed HLK jobs

You can now export a failed job and re-run it on a machine that does not have the HLK Client installed. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/test/hlk/user/exporting-a-failed-hlk-job">Exporting a Failed HLK Job></a>.

### <span id="Support_for_Mobile_testing"></span><span id="support_for_mobile_testing"></span><span id="SUPPORT_FOR_MOBILE_TESTING"></span>Support for Mobile testing

Mobile devices running Test and Health images are now supported for testing with the HLK. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/test/hlk/getstarted/hlk-proxy-client-getting-started-guide">HLK Proxy Client Getting Started Guided</a>.

### <span id="SQL_Server_2012_Express_SP2"></span><span id="sql_server_2012_express_sp2"></span><span id="SQL_SERVER_2012_EXPRESS_SP2"></span>SQL Server 2012 Express SP2

The HLK setup process now installs SQL Server 2012 Express SP2 if no other SQL installation is present on the controller at the time of installation.

### <span id="Scenario_Testing"></span><span id="scenario_testing"></span><span id="SCENARIO_TESTING"></span>Scenario Testing

Test levels have been replaced by Development Phases to better align with the hardware and system development cycle. Tests are organized by their applicability during Bring Up, Development and Integration, Reliability, and Tuning and Validation.

### <span id="Playlists"></span><span id="playlists"></span><span id="PLAYLISTS"></span>Playlists

Playlists describe a collection of tests and can be created from the HLK Studio and <a href="https://docs.microsoft.com/en-us/windows-hardware/test/hlk/api/microsoftwindowskitshardwareobjectmodel">Object Model</a> to define custom test passes.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/afc1a262-6147-448f-910c-dbb1bcb18d07?autoplay=false]

Learn more about playlists in the <a href="https://docs.microsoft.com/en-us/windows-hardware/test/hlk/getstarted/step-6-select-and-run-tests">Getting Started Guide</a>.

### <span id="Windows_Hardware_Compatibility_Program"></span><span id="windows_hardware_compatibility_program"></span><span id="WINDOWS_HARDWARE_COMPATIBILITY_PROGRAM"></span>Windows Hardware Compatibility Program

Hardware certification is no longer required. Instead, the Windows Hardware Compatibility Program is an optional program in which you can participate. For more information, see [Windows Hardware Compatibility Program](https://docs.microsoft.com/en-us/windows-hardware/design/compatibility/).

-   Compatibility Playlist - Levels are no longer used to identify tests required for the Compatibility Program. To create a Compatibility Program test pass, download the official [Hardware Compatibility Program Playlist](https://go.microsoft.com/fwlink/?linkid=875150) and apply to your HLK project.
-   [Windows Hardware Certification blog](http://blogs.msdn.com/b/windows_hardware_certification) -This blog provides up-to-date news about the Windows Compatibility Program. Including Compatibility Playlist update announcements.

### <span id="OS_Support"></span><span id="os_support"></span><span id="OS_SUPPORT"></span>OS Support

The Hardware Lab Kit supports Windows 10 testing only. Use the Hardware Certification Kit for testing downlevel operating systems.

### <span id="Merge_.hckx_Packages"></span><span id="merge_.hckx_packages"></span><span id="MERGE_.HCKX_PACKAGES"></span>Merge .hckx Packages

To support unified driver submissions, results from HCK and HLK projects can be merged together using HLK Studio. When merging, open the HLK project or package first, and then merge in the HCK package(s).

### <span id="Virtual_machine_support"></span><span id="virtual_machine_support"></span><span id="VIRTUAL_MACHINE_SUPPORT"></span>Virtual machine support

The HLK Controller now supports installation and execution in a virtual machine. When configuring your virtual machines, ensure the virtual machine meets the <a href="https://docs.microsoft.com/en-us/windows-hardware/test/hlk/getstarted/windows-hlk-prerequisites">minimum requirements</a> for the HLK Controller.

### <span id="Partial_packaging"></span><span id="partial_packaging"></span><span id="PARTIAL_PACKAGING"></span>Partial packaging

You can now package a subset of test results within an HLK project, tailoring the packaging experience to key scenarios. This allows you to capture, share, and diagnose test failures without having to run tests individually in a new project.

To use this feature, select one or more tests from the **Test** tab, right-click the selection, and choose **Create Partial Package of Highlighted Tests**. Note that this package will be saved as a partial package (.hlkp). This extension will be deprecated in future HLK releases.

### <span id="Rate_this_Test"></span><span id="rate_this_test"></span><span id="RATE_THIS_TEST"></span>Rate this Test

You can now provide feedback on tests in the HLK. To rate tests, you must opt-in to CEIP. To rate a test, right-click on the desired test in the Results Pane, and select Rate This Test.

### <span id="Preview_pane"></span><span id="preview_pane"></span><span id="PREVIEW_PANE"></span>Preview pane

The **Preview pane** in File Explorer provides project and package information including Name, Creation Date, Targets, and Type.

To use the Preview pane in File Explorer, choose the **View** menu group, and then choose **Preview pane**. You can then choose any .hlkx file to view details of the package.

### <span id="64-bit_SQL"></span><span id="64-bit_sql"></span><span id="64-BIT_SQL"></span>64-bit SQL

The HLK now supports 64-bit SQL editions exclusively. Previously, the HCK supported only 32-bit SQL editions exclusively.


 

 






