---
title: DISM API Troubleshooting
description: DISM API Troubleshooting
ms.assetid: 5fae3967-87d7-4e80-8b52-15a9a38f592f

ms.date: 10/25/2017
ms.topic: article


---

# DISM API Troubleshooting


The Deployment Image Servicing and Management (DISM) API allows you to build customized solutions on the DISM platform. You can troubleshoot your solution in development by reviewing the errors and warnings in the DISM API log file. You can change the location and the level of information you want to receive for the log file during your call to the [DismInitialize Function](disminitialize-function.md).

For more information about best practices when coding with the DISMAPI, see [Using the DISM API](using-the-dism-api.md).

## <span id="DISMAPI_Error_Messages"></span><span id="dismapi_error_messages"></span><span id="DISMAPI_ERROR_MESSAGES"></span>DISMAPI Error Messages


The following DISMAPI messages may be reported in the log files when an error occurs.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Message ID</th>
<th>Message Text</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DISMAPI_E_DISMAPI_ALREADY_INITIALIZED</p></td>
<td><p>DISM API was already initialized for this process</p></td>
</tr>
<tr class="even">
<td><p>DISMAPI_E_DISMAPI_NOT_INITIALIZED</p></td>
<td><p>DISM API was not initialized for this process</p></td>
</tr>
<tr class="odd">
<td><p>DISMAPI_E_SHUTDOWN_IN_PROGRESS</p></td>
<td><p>A DismSession was being shutdown when another operation was called on it</p></td>
</tr>
<tr class="even">
<td><p>DISMAPI_E_OPEN_SESSION_HANDLES</p></td>
<td><p>A DismShutdown was called while there were open DismSession handles</p></td>
</tr>
<tr class="odd">
<td><p>DISMAPI_E_INVALID_DISM_SESSION</p></td>
<td><p>An invalid DismSession handle was passed into a DISMAPI function</p></td>
</tr>
<tr class="even">
<td><p>DISMAPI_E_INVALID_IMAGE_INDEX</p></td>
<td><p>An invalid image index was specified</p></td>
</tr>
<tr class="odd">
<td><p>DISMAPI_E_INVALID_IMAGE_NAME</p></td>
<td><p>An invalid image name was specified</p></td>
</tr>
<tr class="even">
<td><p>DISMAPI_E_UNABLE_TO_UNMOUNT_IMAGE_PATH</p></td>
<td><p>An image that is not a mounted WIM or mounted VHD was attempted to be unmounted</p></td>
</tr>
<tr class="odd">
<td><p>DISMAPI_E_LOGGING_DISABLED</p></td>
<td><p>Failed to gain access to the log file user specified. Logging has been disabled</p></td>
</tr>
</tbody>
</table>

 

## <span id="Windows_Error_Messages"></span><span id="windows_error_messages"></span><span id="WINDOWS_ERROR_MESSAGES"></span>Windows Error Messages


Standard Windows errors may also be reported during a DISMAPI process. You can obtain more information about any listed Win32® system error codes by typing `net helpmsg` on the command line and, then typing the error code number. For more information about System Error Codes, see [System Error Codes (0-499)](http://go.microsoft.com/fwlink/?LinkId=147060).

## <span id="related_topics"></span>Related topics


[Using the DISM API](using-the-dism-api.md)

 

 




