---
title: Using Device Fundamentals Tests to Reproduce Device Manager Problem Codes
description: Using Device Fundamentals Tests to Reproduce Device Manager Problem Codes


ms.date: 10/11/2018
ms.topic: article


---

# Using Device Fundamentals Tests to Reproduce Device Manager Problem Codes

The Device Fundamentals (DevFund) tests use Microsoft-supplied I/O plug-ins to exercise devices by sending device class-specific I/O to the device while disabling and enabling the device, cycling the system through power states and reboots, deallocating and reallocating resources, and other tasks.

## Step 1: Determine which tests can potentially reproduce the device error code

The following table matches device problem codes to tests known to exercise a device in such a way as to induce the corresponding problem code. This chart can be used by device and driver testers in an attempt to reproduce device problems seen in the wild, or problems which may be hard to reproduce during regular testing.

| **Device Error Code**        | **Device Error Message**             | **Device Fundamentals Test**                   |                             
|------------------------------|--------------------------------------|------------------------------------------------|
| [10](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-failed-start) | [CM\_PROB\_FAILED\_START](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-failed-start)| [DF - PNP Rebalance Fail Restart Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn941789(v=vs.85).aspx)<br>[DF - PNP Surprise Remove Device Test (Development and Integration)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn940526(v=vs.85).aspx)<br>[DF - PNP Surprise Remove Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn941905(v=vs.85).aspx)<br>[DF - PNP DIF Remove Device Test (Reliability)](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/731f7bde-e2da-4aab-8e35-3715fa405da7)<br>[DF - Reboot restart with IO before and after (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn929617(v=vs.85).aspx)<br>[DF - PNP Cancel Remove Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn929340(v=vs.85).aspx)<br>[DF - PNP Disable And Enable Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn929657(v=vs.85).aspx)<br>[DF - PNP Rebalance Request New Resources Device Test (Development and Integration)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn942119(v=vs.85).aspx)<br>[DF - PNP Rebalance Request New Resources Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn941596(v=vs.85).aspx)<br>[DF - PNP Remove Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn942064(v=vs.85).aspx)<br>[DF - PNP Stop (Rebalance) Device Test (Development and Integration)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn941324(v=vs.85).aspx)<br>[DF - PNP Stop (Rebalance) Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn940665(v=vs.85).aspx)<br>           [DF - Sleep with IO During (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn929660(v=vs.85).aspx)<br>[DF - PCI Root Port Surprise Remove Test (PCI devices only) (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn942131(v=vs.85).aspx)            |
| [14](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-need-restart)               | [CM\_PROB\_NEED\_RESTART](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-need-restart)                               | [DF - PNP Remove Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn942064(v=vs.85).aspx)<br>           [DF - PNP DIF Remove Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn929420(v=vs.85).aspx)                                       |
| [28](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-failed-install)             | [CM\_PROB\_FAILED\_INSTALL](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-failed-install)                           | [DF - PNP DIF Remove Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn929420(v=vs.85).aspx)                                      |
| [31](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-failed-add)                 | [CM\_PROB\_FAILED\_ADD](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-failed-add)                                   | [DF - PNP DIF Remove Device Test (Reliability)](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/731f7bde-e2da-4aab-8e35-3715fa405da7)<br>[DF - PNP Disable And Enable Device Test (Reliability)](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/9d4e2811-1007-445b-b2bd-a2e0ac8468d2)<br>[DF - PNP Rebalance Fail Restart Device Test (Reliability)](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/d5b9e51a-b1fc-4336-b12c-17215c20956d)<br>[DF - PNP Remove Device Test (Reliability)](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/ead2222e-4485-4bfc-84cd-43ac0d2e8181)                                       |
| [38](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-driver-failed-prior-unload) | [CM\_PROB\_DRIVER\_FAILED\_PRIOR\_UNLOAD](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-driver-failed-prior-unload) | [DF - PNP DIF Remove Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn929420(v=vs.85).aspx)                                      |
| [39](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-driver-failed-load)         | [CM\_PROB\_DRIVER\_FAILED\_LOAD](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-driver-failed-load)                  | [DF - PNP DIF Remove Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn929420(v=vs.85).aspx)                                      |
| [43](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-failed-post-start)          | [CM\_PROB\_FAILED\_POST\_START](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-failed-post-start)                    | [DF - PNP Cancel Stop Device Test (Reliability)](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/af6dc68b-da92-41aa-a538-fe2f73c2cb71)<br>[DF - PNP Cancel Remove Device Test (Reliability)](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/6b6a633f-6042-44db-888f-8fcc6381fb98)<br>[DF - PNP Rebalance Fail Restart Device Test (Reliability)](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/d5b9e51a-b1fc-4336-b12c-17215c20956d)<br>[DF - PNP Rebalance Request New Resources Device Test (Reliability)](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/c71001f9-0751-428a-9c21-eb2a77baf0ff)<br>[DF - PNP Remove Device Test (Reliability)](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/ead2222e-4485-4bfc-84cd-43ac0d2e8181)<br>[DF - Sleep with IO During (Reliability)](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/9d87d997-f451-4a3d-852c-90367d4d3864)                                            |
| [52](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-unsigned-driver)            | [CM\_PROB\_UNSIGNED\_DRIVER](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/cm-prob-unsigned-driver)                         | [DF - PNP Disable And Enable Device Test (Reliability)](https://msdn.microsoft.com/en-us/library/windows/hardware/dn929657(v=vs.85).aspx)                              |

See [Device Manager Error Messages](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/device-manager-error-messages) for the list of device error codes.

See [Device.DevFund tests](device-devfund-tests.md) for the complete list of Device Fundamentals tests.

## Step 2: Determine how to configure the test and test machine

After determining which test to run, decide how to configure the test and the test machine to reproduce the error.  To see which parameters are supported by each test, click the link for a specific test in the table above.  This will describe the test and the options available for that test.  For example, some device PnP errors are sporadic.  The /testcycles switch can be used with all tests to specify how many times the test should run:

```
/p:testcycles=10
```

Running the test with more iterations may increase the likelihood of inducing the device error.

Some tests will cause SetupAPI logs to be generated (e.g. [DF - Reinstall with IO Before and After (Reliability)](8dd417ab-e523-4bf0-a971-7c27d99ff5b2.md).  The test machine can be configured to generate [verbose SetupAPI logs](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/review-common-device-fundamentals-reliability-test-failures#span-idnumberofdeviceschangedspanspan-idnumberofdeviceschangedspantest-log-message-number-of-devices-found-after-reboot-1-is-not-the-same-as-before-the-reboot-2-please-review-logs-to-find-the-missing-devices).

## Step 3: Run the test

These tests [can easily be run on the command line](reproduce-the-test-failure-by-running-the-test-from-the-command-line.md) or the HLK after setting up an [HLK Controller](https://docs.microsoft.com/en-us/windows-hardware/test/hlk/getstarted/windows-hlk-getting-started).

Running tests on the command line via te.exe allows for more test options than running the tests via the HLK.  For example, the [/breakonerror](https://docs.microsoft.com/en-us/windows-hardware/drivers/taef/te-exe-command-line-parameters#breakonerror) command line parameter causes TAEF to break into the debugger when an error occurs in the test.  There are many more [command line options](https://docs.microsoft.com/en-us/windows-hardware/drivers/taef/te-exe-command-line-parameters) which can be supplied to te.exe when running tests on the command line.  

## Step 4: Debug the issue

There is a lot of help available for investigating device and driver problems. See the [troubleshooting documentation](troubleshooting-device-fundamentals-reliability-testing-by-using-the-windows-hck.md) for information on reviewing test logs and using the kernel debugger to investigate device and driver problems.
