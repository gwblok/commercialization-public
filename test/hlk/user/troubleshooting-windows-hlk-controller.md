---
title: Troubleshooting Windows HLK Controller
description: Troubleshooting Windows HLK Controller
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8699fee6-9934-41ff-bbfe-32d1e3084dd2


ms.date: 10/15/2017
ms.topic: article


---

# Troubleshooting Windows HLK Controller


This topic describes how to troubleshoot issues with the Windows Hardware Lab Kit (Windows HLK) Controller.

For help with problems that occur during Windows HLK Controller setup, see [Troubleshooting Windows HLK Setup](troubleshooting-windows-hlk-setup.md).

## <span id="adddtest"></span><span id="ADDDTEST"></span>Cannot add test clients after installing the Windows HLK


After installing Windows HLK, the Windows HLK Controller cannot access the HLKJobs database. This prevents the Windows HLK Controller from responding to new clients or sending updates to existing clients.

To fix this problem, stop and restart the **MSSQLServer** service on the Windows HLK Controller by using Services Management Console (From a command prompt, type services.msc). The **MSSQLServer** service should be set to **Automatic**.

## Transaction log is too large (standalone SQL Server 2012)

When using the HLK with standalone SQL Server 2012, if you find that your transaction log is growing too large or too fast, [you may need to adjust your recovery configuration.](microsoft-sql-server-options.md#using-the-hlk-with-standalone-sql-server-2012)


## <span id="unsup"></span><span id="UNSUP"></span>Unsupported scenarios


You must uninstall and reinstall the Windows HLK Controller if you make any of the following changes:

-   Rename the Windows HLK Controller computer.

-   Remove the Windows HLK Controller computer from a domain and add it to a workgroup.

-   Remove the Windows HLK Controller computer from a workgroup and join it to a domain.

## <span id="related_topics"></span>Related topics


[Troubleshooting the Windows HLK Environment](troubleshooting-the-windows-hlk-environment.md)

 

 







