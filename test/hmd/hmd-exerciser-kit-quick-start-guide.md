---
title: HMD Exerciser Kit Quick Start Guide

description: The HMD Exerciser Kit automates validation of mixed reality (MR) head mounted displays (HMDs) and PCs.
keywords:
- HMD, testing
- head mounted display, testing
- HDMI USB testing 

ms.date: 1/10/2018
ms.topic: article


---

# HMD Exerciser Kit Quick Start Guide

To start using the Windows MR HMD Exerciser Kit:

1.  Prepare the system under test (SUT) by installing Windows 10 with the Fall Creators Update or newer. The Windows version should be 1709 or greater. You can check the installed version of Windows by running **winver** from a command prompt. 

2.  Ensure the SUT has a Windows Mixed Reality capable graphics card. Note that a monitor must be plugged in to the SUT in addition to the HMD for Mixed Reality to work.

3.  Remove the HMD Exerciser Main Board and HMD Tester Board from the box, along with any other included cables or accessories.

4.  Connect the HMD Exerciser Main Board's USB 3.0 Type B Connection (labeled **J1**) to a USB 3.0 port on the SUT.

5.  Connect the HMD Exerciser Main Board's HDMI Port labeled **J1** to the Windows Mixed Reality-capable graphics card.

6.  Connect the HMD's USB cable to port **J2** on the USB Type A SuperSpeed Shield.

7.  Connect the HMD's HDMI cable to port **J2** on the HDMI Shield.

8.  If the HMD has an audio jack, connect the HMD audio jack to the HMD Exerciser Main Board using a 3.5mm audio cable.

9.  Connect the HMD Exerciser's USB 2.0 port to the SUT.

    > [!NOTE] 
    > If running the test from a separate host PC, connect the USB 2.0 cable to that system instead.

10. Connect the HMD Exerciser's power supply to the power jack of the bottom board. Do not plug a power supply into the upper power jack unless using servos.

11. Secure the HMD Tester Board to the HMD using the example 3D model or a custom fixture to fit the HMD under test.

    > [!NOTE]
    > If you use a custom fixture, ensure the IR LED and photodiode are positioned in front of the presence sensor, about 1-2cm away. The color sensors should be roughly centered on the displays.

12. Plug in the HMD Board Cable from the HMD Tester Board to the HMD Exerciser's connector labeled **P1.**

13. Extract the HMD Exerciser Kit software locally.

14. Open a command prompt, and navigate to the HMD Exerciser Kit software directory.

15. In the command prompt, run **ConnExUtil.exe /SetPort J2**. The HMD will enumerate and launch the Windows Mixed Reality Portal.

16. In the command prompt, run **ConnExUtil.exe /SetHDMIPort J2**. MRP will show the **Ready** status

17. Test setup is now complete. You can now use ConnExUtil to connect/disconnect the USB and HDMI, get the displays' color and brightness, spoof user presence, and check the audio levels.
