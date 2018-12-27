---
title: Troubleshooting Windows Assessment Services
description: Troubleshooting Windows Assessment Services
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f0a1c2cb-9566-4451-a201-5dab89c7a0b9
ms.mktglfcycl: plan
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# Troubleshooting Windows Assessment Services

The following information can help you troubleshoot common problems.


## Log information

You can potentially find the cause of certain problems by checking the information logs that are created during certain processes. The following table describes the various logs that can be viewed and where they can be viewed (in a file/folder or the Event Viewer, and on the server or the test computer/client):

Location type          | Location                                                                                               | Log type(s)
:--------------------- | :----------------------------------------------------------------------------------------------------- | :----------
Event Viewer on client | **Applications and Services Logs > Windows Assessment Services Client**                                | Errors from the UI
Client file            | **%SystemRoot%\\System32\\WinEvt\\Logs\\Windows Assessment Services Client.evtx**                      | Errors from the UI (alternate viewing location)
Event Viewer on server | **Applications and Services Logs > Microsoft > Windows > Windows Remote Management**                   | Windows Remote Management (WinRM) log
Event Viewer on server | **Applications and Services Logs > Microsoft > Windows > Windows Deployment Services Diagnostics**     | Windows Deployment Services (Windows DS) issues (on Windows Server 2012)
Server file            | **%SystemRoot%\\Tracing\\WDSServer.log**                                                               | Windows DS issues (on Windows Server 2008 R2)
Server file            | **C:\\Windows\\Temp\\RelaxService.TraceListener.Tracing**                                              | Windows Assessment Services events
Server file            | **%SystemDrive%\Relax\\\<GUID>\Job\Results.log**                                                       | Location of the results folder where the results are saved on the client (if the results are not copied to the server)
Server folder          | **C:\\Relax\\Logs**                                                                                    | Client log files when a client is added to the server inventory
Server folder          | **%SystemDrive%\\Relax\\Logs**                                                                         | Image deployment logs from the Windows Preinstallation Environment (Windows PE)

> [!NOTE]
> To enable Windows DS logging on Windows Server&nbsp;2008&nbsp;R2, you must set the **HKLM\\System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE** registry key's **TracingDisabled** entry to `0` and the **HKLM\\Software\\Microsoft\\Tracing\\WDSServer** registry key's **EnableFileTracing** entry to `1`.


## Symbol server setup

Some assessments require access to symbols. In some cases the information in the assessment results can be incorrect or have missing information if a symbol server is not available. In many cases this dependency is satisfied by Internet connectivity and access to the Microsoft public symbols server. In other cases where connectivity to the Internet is not available such as a lab environment, you can set up a private symbols server or install the symbols on the local computer to get the full benefits of the assessments.

**To set the symbols environment variable on a test computer:**

1.  Open File Explorer, right-click **Computer**, and select **Properties**.

2.  In the Properties window click **Advanced System Settings**.

3.  In the Systems Properties window, on the **Advanced** tab, click **Environment Variables**.

4.  Under System variables, click **New** to set the symbols environment variable by using one of the following paths:

    1.  The public symbols server (requires Internet connection)

        Connect the computer to the Internet so that it can access the Microsoft symbols server, and then configure the \_NT\_SYMBOL\_PATH environment variable to use the Microsoft symbols server at **http://msdl.microsoft.com/downloads/symbols**.

    2.  A network connected symbols path (requires local network connection)

        Connect the computer to the local intranet and then configure the \_NT\_SYMBOL\_PATH environment variable to use an intranet symbols path.

    3.  A local symbols path

        Download the symbols to the Windows Assessment Services server computer, and point the test computer to this location by setting the \_NT\_SYMBOL\_PATH environment variable to use a path to the symbols on the server, such as **\\\\WASServer\\relax\\symbols**.

**To set up internal symbols:**

1.  Install the ADK, and initialize WAS.

2.  Get an IPsec boundary exception for the WAS server machine. This will ensure that WAS test machines are able to access the Relax share.

3.  Join the WAS server machine to the domain.

4.  Add a domain user to the WAS server machine into the Administrators group that has access to internal symbol server.

5.  Stop the WAS service by running the following command from an elevated command prompt:

    ```
    net stop WASSVC
    ```

6.  Change the service logon account to the new domain account.

7.  Run the following command from an elevated command prompt, replacing &lt;*path to internal symbols*&gt; with the appropriate path:

    ```
    SETX_NT_SYMBOL_PATH \\<path to internal symbols> /M
    ```

8.  Restart the machine.

For more information about how to set the symbols path and download symbols, see [MSDN: Symbols Support](http://go.microsoft.com/fwlink/?LinkId=235359). For information about how to troubleshoot missing symbols, see [Common In-Depth Analysis Issues](common-in-depth-analysis-issues.md#missingsymbols).


## Common problems

Here are some common problems that may occur with Windows Assessment Services.


### The client cannot connect to the server

If the Windows Assessment Services - Client (Windows ASC) cannot connect to the server, you might receive the following error message:

`Unable to connect to the remote server: A connection attempt failed because the connected party did not properly respond after a period of time, or an established connection failed because the connected host has failed to respond.`

Check the server status by using the `sc query wassvc` command. If the server is not running, start the service by using the `net start wassvc` command.

> [!WARNING]
> The `sc query` command only works if it is run on the Windows Assessment Services server.


### The test computer already exists in inventory

If you receive the following message, the test computer already exists in the Windows Assessment Services inventory:

`Execute any scenario manually. Hit Exit to Reboot`

If you do not see the computer entry in the Server Inventory window, close and then re-open that window to refresh the content.


### The Run button is unavailable

If the **Run** button is unavailable, make sure that you have selected specific computers and images in the **Assets** details. If you have selected specific computers and images, but you do not see any assessments on the **Results** page, close and then re-create the current job.


### The inventory test computer fails with WS\_E\_OPERATION\_TIMED\_OUT

If you receive the following error:

`Error updating machine configuration in RelaxServer. Please check that the server is available and try again later. (ErrorCode:-2143485946)`

Check the error log at **C:\\Relax\\CompleteDeployment.log** for additional error details and rerun **CompleteDeployment.cmd**.


### An image deployment failure does not have enough information on the monitoring page

If you receive the error message `Error code: Exiting Scenario Deploy: ErrorId=<IDNumber>`, an image deployment may have failed, and there is not enough information about the failure on the monitoring page. The following table shows some common error ID numbers and the errors that they represent:

| Error ID number | Error description                                                                                                                   |
| --------------: | :---------------------------------------------------------------------------------------------------------------------------------- |
| 2               | Either you are using an image of unsupported format, the unattend answer file is missing, or the image file is missing.             |
| 38              | The image file is corrupted.                                                                                                        |
| 87              | Bcdboot failed to update the BCD store. This is specific to some UEFI computer prototypes. No workaround is available at this time. |
| 193             | Bcdboot failed to update the BCD store. An image of incompatible architecture was applied to a test computer.                       |
| -2147024809     | Diskpart failed to find any hard disk drive that could be used to apply an image to.                                                |


### A DISM error occurs during computer inventory

If you receive the following error while taking inventory of a computer, you must use the x86 Windows PE image for the bootable USB drive that you created for inventory.

`An error occurred. You cannot service an x86-based image from an x64-based host that does not support WOW64. Try the operation again from a host environment that supports WOW64. 
Error running Driver Scavenge. ErrorCode 193.`

When you inventory a computer, driver information is gathered and stored at **%SystemDrive%\\relax\\driver** using DISM. DISM cannot run the driver servicing command on an X86 Windows image, from a Windows PE X64 environment. For more information, see DISM Supported Platforms.

To fix the problem, use (or create) a bootable USB drive created for X86 architecture. For more information, see [Windows Assessment Services Setup and Configuration](windows-assessment-services-setup-and-configuration-wastechref.md).


### The test computer does not work after changing the server name

If you rename the Windows Assessment Services server and re-initialize it, you must redeploy Windows on the test computer before you run additional assessments.


### The test computer cannot be reached

When running assessments remotely, Windows Assessment Services relies on DNS to resolve the test computer names. If DNS has duplicate entries for the same computer name, one from a domain joined computer and another from a workgroup computer, Windows and WinRM will pick the computer that DNS resolves to.

If you receive an error that includes `Machine Not Reachable`, check the DNS entries for duplicates.

> [!NOTE]
> The computer name must contain only alphanumeric characters and dashes. If the computer name contains an underscore or other extended characters, the computer may not be discoverable via Domain Name System (DNS).


### A push notification fails when running Windows ASC from a server without Windows Assessment Services

If you are running Windows ASC on a Windows server and you do not have Windows Assessment Services installed on that server, push notifications will fail to enable in Windows ASC when you launch it.

You can work around the problem on the server where Windows ASC is installed by enabling the optional component MSMQ-Server, using the following DISM command from an elevated command prompt.

```
Dism /Online /Enable-Feature:MSMQ-Server
```

Alternatively, you can run Windows ASC on a client computer or on the same server where Windows Assessment Services is installed.


### The dumps folder does not contain any dump files

By default, dump files are not copied to the server after assessment runs. If you want to collect dumps for assessment runs, edit **&lt;Relax&nbsp;directory&gt;\\Scripts\\Harnesses\\Axe\\CompleteAssessment.cmd**, and change the value for set\_copydumpstoserver to `true`. By default, this value is `false`.


## Related topics

[Windows Assessment Services](windows-assessment-services-technical-reference.md)

