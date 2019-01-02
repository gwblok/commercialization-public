---
title: Reproduce the test failure by running the test from the command line
description: Reproduce the test failure by running the test from the command line
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d10a52eb-5275-4f2b-88ea-72dbc3007cb2


ms.date: 10/11/2018
ms.topic: article


---

# Reproduce the test failure by running the test from the command line


It is sometimes convenient to reproduce test failures by running the tests from command line.  The following documentation assumes that the Hardware Lab Kit (HLK) has already been installed on the controller machine.

## <span id="cmdline"></span><span id="CMDLINE"></span>Run a Device Fundamentals test from the command line


**To run a Device Fundamentals test from the command line:**

1. Create a **c:\\temp** folder on the system under test (SUT).

2. Copy all files from **\\\\**&lt;<em>hckcontroller</em>**&gt;\\taefbinaries\\**&lt;*arch*&gt; folder to **c:\\temp** on the SUT.

   Where &lt;*hckcontroller* is the name of the Windows Hardware Lab Kit (Windows HLK) controller, and &lt;*arch*&gt; is the SUT platform.

3. To install and start the [TAEF](https://docs.microsoft.com/en-us/windows-hardware/drivers/taef/) service, type the following commands from a command prompt:

   1.  Go to the 'temp' folder created above:

       On X86 or X64: cd c:\\temp

       On ARM or ARM64: cd c:\\temp\MinTe

   2.  wex.services.exe /install:Te.Service

   3.  sc start Te.Service

4. Copy all files from **\\\\**&lt;<em>hckcontroller</em>**&gt;\\tests\\**&lt;*arch*&gt;\\DevFund\\ directory to **c:\\temp**.

5. Change directory to **c:\\temp** and run the following command (note that Te.exe lives in **c:\\temp\\MinTe** on ARM and ARM64):

   ``` syntax
   c:\temp\Te.exe Devfund_<testname>.dll /name:"<test case name>" /p:"DQ=DeviceID='<Device Instance Path of device under test from Device Manager>'" /RebootStateFile:state.xml
   ```

   Where &lt;*test case name*&gt; is the name of the test in the test binary.

   The /**name** switch is optional. Since some test binaries contain multiple tests, the /**name** switch specifies which tests should be run.  If unspecified, all tests contained in the test binary are executed in sequence.  The list of tests in a test binary can be obtained by running the following command:

   ``` syntax
   Te.exe Devfund_<testname>.dll /list
   ```

   For example, the Devfund_PnPDTest.dll contains most of the PnP-related tests:

   ```
   c:\temp>Te.exe Devfund_PnPDTest.dll /list
   Test Authoring and Execution Framework v10.21 for x64

       c:\temp\Devfund_PnPDTest.dll
           PNPDTest
               PNPDTest::PNPDisableAndEnableDevice
               PNPDTest::PNPRemoveAndRestartDevice
               PNPDTest::PNPCancelRemoveDevice
               PNPDTest::PNPCancelStopDevice
               PNPDTest::PNPTryStopAndRestartDevice
               PNPDTest::PNPTryStopDeviceRequestNewResourcesAndRestartDevice
               PNPDTest::PNPTryStopDeviceAndFailRestart
               PNPDTest::PNPSurpriseRemoveAndRestartDevice
               PNPDTest::PNPDIFRemoveAndRescanParentDevice
               PNPDTest::DisableEnhancedDeviceTestingSupport
   ```
    
   The command to run a single test from this test binary might look like this:

   ``` syntax
   c:\temp\Te.exe Devfund_PnPDTest.dll.dll /name:PNPDTest::PNPSurpriseRemoveAndRestartDevice /p:"DQ=DeviceID='my\device\id'" /RebootStateFile:state.xml
   ```

   The name of the test in the test binary will not be exactly the same as the title of the test.  For a mapping of test binary names to HLK test names, see [Device.DevFund tests](device-devfund-tests.md).

****

## <span id="How_to_use__BreakOnError_to_break_into_the_debugger"></span><span id="how_to_use__breakonerror_to_break_into_the_debugger"></span><span id="HOW_TO_USE__BREAKONERROR_TO_BREAK_INTO_THE_DEBUGGER"></span>How to use /BreakOnError to break into the debugger


If the "Run Test" task in a Device Fundamentals test fails and you want to review the system state in the kernel debugger at the same time that the test logs a failure, you can run the test manually from a command prompt together with the kernel debugger and pass the **/BreakOnError** command line switch to **Te.exe**.

Running Te.exe with the **/BreakOnError** switch causes the system to break into the kernel debugger when the test is ready to log an error. For more information on setting up a kernel debugger, see [Setting Up Kernel-Mode Debugging Manually](http://go.microsoft.com/fwlink/?LinkID=299467).

To run a Device Fundamentals test with the /**BreakOnError** switch, add the switch as shown below:

``` syntax
Run c:\temp\Te.exe Devfund_<testname>.dll /p:"DQ=DeviceID='<Device Instance Path of device under test from Device Manager>'" /RebootStateFile:state.xml /BreakOnError /name:"*<test case name>*"
```

Where &lt;*test case name*&gt; is the name of the test.

## <span id="Example_debug_scenario"></span><span id="example_debug_scenario"></span><span id="EXAMPLE_DEBUG_SCENARIO"></span>Example debug scenario


You can investigate the following failure by re-running the test and having the system break into the debugger when the test logs the failure on re-run.

``` syntax
WDTF_FUZZTEST             : INFO  :    Running IOCTL Fuzzing Test on surface \DosDevices\usb#vid_045e&pid_f0ca&mi_00#7&12099dde&0&0000#{0b9f1048-b94b-dc9a-4ed7-fe4fed3a0deb}\{8de0ff21-6c06-4c27-bfe0-e62612c015ae}. Access Mode=NO SYNC. Open Type=TREE_CONNECT. Opened with access 1201bf 

WDTF_FUZZTEST             : ERROR :    Test thread exceeded timeout limit. Terminating thread

WDTF_FUZZTEST             : ERROR :    Last logged operation: ZwDeviceIoControlFile, CtrlCode=0x22e10b, InBuf=0xfffffc00, 0 OutBuf=0xfffffc00, 0

WDTF_FUZZTEST             : INFO  :    Successfully terminated test thread.
```

You can set a break point in the debugger using the following command:

``` syntax
Te.exe Devfund_FuzzTest_WLK_Certification.dll /p:"DQ=DeviceID='USB\VID_045E&PID_F0CA&MI_00\7&12099DDE&0&0000'" /RebootStateFile:state.xml /BreakOnError /name:"*IOCTLTest*"
```

Device Fundamentals tests run as Te.ProcessHost.exe (if it exists) or as Te.exe (if Te.ProcessHost.exe doesn't exist). Reviewing threads running in these test processes can help with triaging hangs and/or test failures.

You can get the process id of **Te.ProcessHost.exe** by running the following command:

``` syntax
!process 0 0 Te.ProcessHost.exe
```

Switch the process context in the debugger to the test process:

``` syntax
.process /p /r <process id>
```

Dump process info:

``` syntax
!process <process id>
```

## <span id="related_topics"></span>Related topics


[Troubleshooting Device Fundamentals Reliability Testing by using the Windows HLK](troubleshooting-device-fundamentals-reliability-testing-by-using-the-windows-hck.md)

 

 







