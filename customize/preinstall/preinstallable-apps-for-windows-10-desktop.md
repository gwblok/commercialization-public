---
title: Preinstallable apps for desktop devices
description: Learn how to add an app to a Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) image that will be available to customers at first boot.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 047A9971-29C1-402A-8671-C36272EC511B


ms.date: 04/30/2018
ms.topic: article


---
# Preinstallable apps for desktop devices

OEMs and Mobile operators can create Partner applications that can be packaged and configured to install during the initial device setup process. While the user is going through the initial setup process, the preinstalled applications are installed in the background.

The process for creating a preinstalled app is similar to that of a standard app. An unsigned app package (.appx), generated with the Windows SDK, is submitted to the Windows Dev Center for certification and signing. During the submission process, you can specify that you are submitting a preinstalled app. If the app meets certification requirements, it is processed to create a package that can be downloaded from the Dev Center. The app can then be published to the Microsoft Store as well, so that users who have uninstalled the app can re-download it and updates can later be offered to devices that have the app installed.

Some characteristics of preinstalled apps include:

1. They can be published as "hidden" so that the app is not discoverable in the Microsoft Store except through a deep link.
1. They can be updated, as live or hidden to the Microsoft Store. Users with the preinstalled application will get a notification for the update.
1. They can be deleted by the user. They can be reinstalled if published live.
1. They can become obsolete. If a user uninstalls an app that is no longer sold in the Microsoft Store, the user will not be able to reinstall that app.

## Get the Windows ADK

You will need to use the Windows Assessment and Deployment Kit (ADK) to pre-install Microsoft Store apps in your desktop images. [Download the Windows ADK](http://go.microsoft.com/fwlink/p/?LinkId=526740).

## Request a preinstallation package

Once an app has been added to the Dev Center, you can request a preinstallation package for it. If you are the OEM adding this application to your OS image, you would ask the developer of the application to do this on your behalf. They would then give you the downloaded zip file. You cannot access their developer account directly.

1. From the dashboard in Dev Center, select the app that is to be preinstalled. If it is a new app, click **Create new app**.
1. Select **manage published** packages
1. Select **Request package** for OS preinstallation
1. A confirmation dialog will appear, noting that apps preinstalled on an OS prior to Windows 10 must be free. Select **Enable**.
1. Find the correct package for the targeted OS and download by selecting **Download** or **Generate package**.
1. Once ready the link will change to **Download**.
1. Zip file is ready for inclusion in OS image.

## Add the app to the OS image

Applications are considered Assets, which are configurable customizations that are not settings. You can add them using DISM, which is part of the Windows Assessment and Deployment Kit (ADK). In Windows 10, version 1803, you can use DISM to provision apps per region.

For detailed instructions, see [Preinstall apps using DISM](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/preinstall-apps-using-dism).
