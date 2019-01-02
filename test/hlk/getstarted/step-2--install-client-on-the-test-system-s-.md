---
title: Step 2 Install Client on the test system(s)
description: Step 2 Install Client on the test system(s)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: EC5E600B-8E22-4D2D-AEC7-B7DDBD83CB8D


ms.date: 10/15/2017
ms.topic: article


---

# Step 2: Install Client on the test system(s)

After you install the Windows Hardware Lab Kit (Windows HLK) on the test server, you are ready to add test systems to the environment. You must install the Windows HLK Client software on each test system. The Windows HLK Client software is stored on the Windows HLK test server.

If you are testing software, be sure to install the product on the test system first, and then install the Windows HLK Client software.

## To install the Windows HLK Client

1.  On the test system, browse to the following location:

      **\\\\&lt;ControllerName&gt;\\HLKInstall\\Client\\Setup.cmd**.
      <br>(Replace *&lt;ControllerName&gt;* with the name of the test server.)

    If the following software is not already installed, it is installed during this step: 
    -  .NET Framework 4 (Client Profile and Extended) 
    -  Application Verifier 
    -  Windows Driver Test Framework (WDTF)
    -  Windows Performance Toolkit (WPT).

    If the test system has a Server Core installation, then you should install the HLK client using the silent install option:

    ```syntax
    \\<HLKController>\HLKInstall\Client\Setup.cmd /qn ICFAGREE=Yes
    ```         

2.  The **Windows Hardware Lab Kit Client Setup** wizard appears. To start the wizard, choose **Next**.

3.  On the **Internet Connection Firewall Agreement** page, select **Yes I will allow a port to be opened**, and then choose **Next**.

    >[!NOTE]
    >  If the **Internet Connection Firewall Agreement** page doesn't appear, either Windows Firewall isn't installed, or another software firewall or hardware firewall is installed on the computer. If another firewall is installed, you must manually open TCP port 1771 to proceed with installation. Refer to the instructions that came with your firewall product to manually open a TCP port. If you continue without opening port 1771, the installation may fail or the Client software might not function properly.

4.  When the **Ready to Install** page appears, select **Install**.

5.  Click **Finish** to exit the wizard.

    >[!TIP]
    >When installation completes, confirm its success by going to the **Control Panel** and choosing **Uninstall a program**. **Windows Hardware Lab Kit Client** should appear in the program list.

6.  Repeat steps 1-5 for each test system.

 

 






