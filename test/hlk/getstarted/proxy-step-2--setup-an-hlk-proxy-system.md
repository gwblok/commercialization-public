---
title: Step 2 Setup an HLK Proxy System
description: Step 2 Setup an HLK Proxy System
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 25425C6A-D375-4C5A-9A91-5F596DB32E96


ms.date: 10/15/2017
ms.topic: article


---

# Step 2: Setup an HLK Proxy System

Before proceeding, be sure that the credentials of the user on the proxy system match those of an administrator on your HLK controller:
-   Local administrator account on proxy: &lt;ProxyMachineName&gt;\\TestAdmin
-   Local administrator account on controller: &lt;HLKControllerMachineName&gt;\\TestAdmin
-   Both with the same password

1.  On the Proxy system (which may be the same machine as the HLK Controller), run setup.exe from the following location: 

    ```syntax
    \\<ControllerName>\HLKInstall\ProxyClient\setup.exe
    ```
    (Replace &lt;ControllerName&gt; with the name of the test controller.)

2.  The WTT Proxy Setup wizard appears. Follow the instructions in the setup wizard to completion.

1.  Start the Proxy Service by double clicking on the **WTT Proxy** shortcut on the desktop of the proxy system or by navigating to  %ProgramFiles(X86)%\\WTTMobile\\Client\\ and running the following command from the elevated command prompt:  

    ```syntax
    WTTProxy.exe -console
    ```

4.  Leave the elevated command prompt window from the previous step open.






