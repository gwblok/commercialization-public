---

Description: Run custom actions during a feature update
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Run custom actions during a feature update

ms.date: 04/20/2018
ms.topic: article
ms.custom: RS5
---

# Run custom actions during feature update

## Overview

Starting with Windows 10, version 1803, enterprise IT admins can run their own custom actions by running scripts during an upgrade or feature update. 

## Running custom actions

### About custom actions
Custom actions are .cmd scripts that run during the feature update process. These can be run during two phases of an upgrade:
1.  Pre-install phase: This phase is when Setup starts, but prior compatibility checks. Actions during this phase are specified in `preinstall.cmd`.
2.  Pre-commit phase: This phase is prior to the upgrade being applied and the system rebooting. Actions during this phase are specified in `precommit.cmd`.

### Custom actions folder structure

Custom action scripts run from subfolders in `%windir%\System32\update\`, depending on whether you want scripts to run for a single upgrade or on all future upgrades. Windows Setup automatically looks for these scripts in the following locations, and will run them if they are present:

| Folder | Description |
| --- | ---|
| %windir%\System32\update\run | Windows Setup will migrate scripts in these folders so they are run in future upgrades. |
| %windir%\System32\update\runonce | Scripts in this folder will only run in one upgrade and won't be migrated for future upgrades. |
| %windir%\System32\update\run\\\<GUID><p></p>%windir%\System32\update\runonce\\\<GUID> | Create a unique GUID to clearly identify each script you run. Use this GUID to name a folder within the `run` and `runonce` folders.  |
| %windir%\System32\update\run\\\<GUID>\reflectdrivers<p></p>%windir%\System32\update\runonce\\\<GUID>\reflectdrivers | Boot-critical drivers in this folder will be reflected. Make sure the reflectdrivers folder only contains a necessary set of encryption drivers. Having more drivers than necessary can negatively impact upgrade scenarios. See [Device drivers](device-drivers-and-deployment-overview.md#offline) to learn more about reflected drivers. |




If an update fails or has to be rolled back, a failure.cmd script can be used to perform custom operations or undo actions of previous custom scripts. If the scripts fail, the update will fail.


## Custom action script locations and examples

### Script locations

The following table shows the folder path structure of files for running custom actions:


|                  Run (Scripts will be migrated)                   |                 Run Once (scripts won't be migrated)                  |
|-------------------------------------------------------------------|-----------------------------------------------------------------------|
|       %windir%\System32\update\run\\\<GUID>\preinstall.cmd        |       %windir%\System32\update\runonce\\\<GUID>\preinstall.cmd        |
|        %windir%\System32\update\run\\\<GUID>\precommit.cmd        |        %windir%\System32\update\runonce\\\<GUID>\precommit.cmd        |
|         %windir%\System32\update\run\\\<GUID>\failure.cmd         |         %windir%\System32\update\runonce\\\<GUID>\failure.cmd         |
| %windir%\System32\update\run\\\<GUID>\reflectdrivers\example1.inf | %windir%\System32\update\runonce\\\<GUID>\reflectdrivers\example2.inf |
| %windir%\System32\update\run\\\<GUID>\reflectdrivers\example1.sys |   %windir%\System32\update\run\\\<GUID>\reflectdrivers\example2.sys   |

### Example file paths and names

| Scenarios                      | File location examples                                                               |
| ------------------------------ | ------------------------------------------------------------------------------------ |
| **Script deployment data**         | %windir%\system32\update\                                                            |
| **Migration directories**      |                                                                                      |
| Scripts that will be migrated  | %windir%\system32\update\run\                                                        |
| Scripts that won't be migrated | %windir%\system32\update\runonce\                                                    |
| **Folder path with a GUID**        | %windir%\system32\update\run\6971CB27-6F59-43CD-A764-969EE9BBCC1C\                   |
| **Script names with GUID**         |                                                                                      |
|                                | %windir%\system32\update\run\6971CB27-6F59-43CD-A764-969EE9BBCC1C\preinstall.cmd     |
|                                | %windir%\system32\update\run\6971CB27-6F59-43CD-A764-969EE9BBCC1C\precommit.cmd      |
|                                | %windir%\system32\update\run\6971CB27-6F59-43CD-A764-969EE9BBCC1C\failure.cmd        |
|                                | %windir%\system32\update\runonce\6971CB27-6F59-43CD-A764-969EE9BBCC1C\preinstall.cmd |
|                                | %windir%\system32\update\runonce\6971CB27-6F59-43CD-A764-969EE9BBCC1C\precommit.cmd  |
|                                | %windir%\system32\update\runonce\6971CB27-6F59-43CD-A764-969EE9BBCC1C\failure.cmd    |
| **Reflected drivers folder**       | %windir%\system32\update\run\6971CB27-6F59-43CD-A764-969EE9BBCC1C\reflectdrivers\    |




