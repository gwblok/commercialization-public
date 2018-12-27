---
title: Microsoft SQL Server Options
description: Microsoft SQL Server Options
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 004bb51b-adb9-41b4-8d1a-df662200029b


ms.date: 10/15/2017
ms.topic: article


---


# Microsoft SQL Server Options

The Windows HLK provides SQL Server Express. If you would prefer to use a different edition of Microsoft SQL Server, the HLK supports 64-bit versions of SQL Server 2012 and SQL Server 2008R2.

Depending on your operating system, you might need to install additional service packs for SQL prior to installing the HLK.

>[!WARNING]
>- The HLK does not support SQL Server 2014. You must uninstall SQL Server 2014 prior to installing the HLK.
>- The HLK does not support 32-bit versions of SQL Server. Any 32-bit instance must be uninstalled prior to installing the HLK.

## Install Microsoft SQL Server 2012 

1.  Enable .NET 2.0/3.x feature from within Server Manager

2. Install SQL using the setup application using the following command line for a unattended install. /QUIET and /HIDECONSOLE flags may be omitted to see any errors that may occur during install.

``` syntax
(setup application) /QUIET /HIDECONSOLE /ACTION=install /FEATURES=SQL,RS /SQLSVCACCOUNT="NT AUTHORITY\SYSTEM" /AGTSVCACCOUNT="NT AUTHORITY\SYSTEM" /AGTSVCSTARTUPTYPE=Automatic /ASSVCACCOUNT="NT AUTHORITY\SYSTEM" /RSSVCACCOUNT="NT AUTHORITY\SYSTEM" /SQLSYSADMINACCOUNTS="BUILTIN\ADMINISTRATORS" "%USERDOMAIN%\%USERNAME%" /INSTANCENAME=MSSQLSERVER /TCPENABLED=1 /NPENABLED=1 /IAcceptSQLServerLicenseTerms=1
```
## Install Microsoft SQL Server 2008R2 

Follow the same procedure for installing Microsoft SQL Server 2012, but before installing SQL via the command line, be sure to do the following:
1. Install SQL Server 2012 SharedManagementObjects.msi (64-bit) from the following link:
<br><http://go.microsoft.com/fwlink/p/?linkid=239659&clcid=0x409>
2. Install SQL Server 2012 SQLSysClrTypes.msi (64-bit) from the following link:
<br><http://go.microsoft.com/fwlink/p/?linkid=239644&clcid=0x409>

 
## Using the HLK with standalone SQL Server 2012

When using the HLK with standalone SQL Server 2012, be aware that some tests can make thousands of database calls. Be sure to choose the right backup configuration and recovery model so that your transaction logs do not grow to be too large.

When using standalone SQL Server 2012, you have a choice of recovery models:
- **Full recovery model** enables point-in-time database recovery.
- **Simple recovery model** can only restore a database from most recent backup. There is no point-in-time recovery.

When the database is configured to simple recovery, previous logs will be truncated and that space will be made available for reuse. When the database is configured to full recovery, the transaction log continues to grow until a backup is performed. This helps provide a point-in-time recovery, but if backups are infrequent, it could generate an extremely large transaction log. If there are enough transactions, the log can become large enough to consume all available storage memory and crash the server.

We recommend using the Simple Recovery model when using the HLK with standalone SQL Server 2012. If you use the Full Recovery model, be sure to perform backups frequently enough that the transaction log size remains manageable.

### Related Topics

- [Transaction Log](https://docs.microsoft.com/en-us/sql/relational-databases/logs/the-transaction-log-sql-server)

- [Recovery Models](https://docs.microsoft.com/en-us/sql/relational-databases/backup-restore/recovery-models-sql-server)







