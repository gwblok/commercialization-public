---
title: Graphics Driver Installation During OS Setup.
description: Graphics Driver Installation During OS Setup.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c419f2c7-f73b-4c0e-b0ad-3110e3529710


ms.date: 11/05/2018
ms.topic: article


---

# <span id="p_hlk_test.6a899432-c2bd-42a7-8afe-1cbebee7aec2"></span>Graphics Driver Installation During OS Setup.


This test verifies that a driver can be injected into an OS image, that it installs during the setup phase of the OS, and is working when the user first boots into the OS during personalization stage. In order to accomplish this the following steps need to be done: 1. Copy an existing build folder to a Windows 8.1 machine. 2. Inject the driver being tested into the image using DISM.exe 3. Enable Test signing in the image file if using test signed drivers. 4. Use the image created to install a test machine. 5. Verify the driver was installed successfully and is working. A dialog prompt requiring user intervention to indicate Pass or Fail will be presented on the HCK client. The script that can be used for creating the OS setup image is located at \\\\\[HCKControllerName\]\\Tests\\amd64\\NTTEST\\windowstest\\tools\\InjectDriversToWim.cmd The script takes the following paramerters: First parameter is the path to the location of the build folder. Second parameter is the location of the folder that contains the drivers to be injected. Example: InjectDriversToWim.cmd "c:\\Build\_9405\\Client" "C:\\MyDrivers\\AMD64" After verifying the script completed successfully installation of the OS can be ran. In the example passed setup.exe contained in the "c:\\Build\_9405\\Client" can be run to install the OS.

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>Device.Graphics.WDDM.DisplayRender.DriverSetupCompatible</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows 10, client editions (ARM64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 5 |
|**Category**| Compatibility |
|**Timeout (in minutes)**| 300 |
|**Requires reboot**| false |
|**Requires special configuration**| true |
|**Type**| automatic |



## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.Graphics additional documentation](device-graphics-additional-documentation.md)

## <span id="More_information"></span><span id="more_information"></span><span id="MORE_INFORMATION"></span>More information


### <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters

| Parameter name               | Parameter description                                |
|------------------------------|------------------------------------------------------|
| **LLU\_NetAccessOnly**       | The name of your machine's LLU                       |
| **ConfigDisplayCommandLine** | Custom Command Line for ConfigDisplay. Default: logo |
| **TDRArgs**                  | /get or /set                                         |



## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](../user/troubleshooting-windows-hlk-test-failures.md).










