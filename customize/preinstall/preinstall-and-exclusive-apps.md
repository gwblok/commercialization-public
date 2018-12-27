---
title: Preinstalled and exclusive apps
description: OEMs and Mobile operators can create Partner applications that can be packaged and configured to install during the initial device setup process. OEMs can also work with software developers to target OEM devices for apps to appear exclusively on, based on the OEM IDs set in the registry.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 268d5950-04e6-4450-94a0-a3d902edc7e7


ms.date: 12/6/2017
ms.topic: article


---
# Preinstalled and exclusive apps

As an OEM, you have a unique opportunity to create applications that ship with your OS image directly to customers. This means you can preinstall applications onto the image, connect them to devices, and promote them in both the Microsoft Store, and your OEM store. You can also promote exclusive apps in your OEM store.

## App design

To make a compelling app that gets your customers to pay attention, follow the design principles that guide the development of great Universal Windows Platform (UWP) experiences. The [Introduction to UWP app design](https://docs.microsoft.com/en-us/windows/uwp/design/basics/design-and-ui-intro) is a great starting place for learning about UWP. From there you should learn about the [controls and control patterns](https://docs.microsoft.com/en-us/windows/uwp/design/controls-and-patterns/index) to use, how to interact with [inputs and devices](https://docs.microsoft.com/en-us/windows/uwp/design/input/input-primer), and how to think about [usability](https://docs.microsoft.com/en-us/windows/uwp/design/usability/index). The [Get Started with Windows Apps](https://developer.microsoft.com/en-us/windows/apps/getstarted) guide in the [Windows Dev Center](https://developer.microsoft.com/en-us/windows/) is another resource you can use to learn more.

## Preinstalled apps

The primary channel for distributing apps is the Microsoft Store. However, because Microsoft Store apps are only available on the device after a user-initiated download and some partner apps need to be available at first boot, there is an alternate option available for OEMs and mobile operators. OEMs and Mobile operators can create Partner applications that can be packaged and configured to install during the initial device setup process. While the user is going through the initial setup process, the preinstalled applications are installed in the background.

## Exclusive apps

By forming relationships with developers, you can work together to publish exclusive apps onto your devices. You have the flexibility based on the contracts you establish with developers to ensure that these apps are available exclusively on your Windows 10-based devices (as identified by OEM Store ID) and don't appear in the general catalog on any other devices.

## In this section

| Topic                                 | Description                                                                          |
|:--------------------------------------|:-------------------------------------------------------------------------------------|
| [Preinstallable apps for desktop devices](preinstallable-apps-for-windows-10-desktop.md)  | Learn how to add an app to a Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) image that will be available to customers at first boot.                                |
| [Preinstallable apps for mobile devices](preinstallable-apps-for-window-10-for-phones.md) | Learn how to add an app to a mobile image that will be available to customers at first boot.                                                                                          |
| [Preinstall tasks](preinstall-tasks.md)                                                   | OEMs and MOs are permitted to ship preinstalled apps in the device image. Some of those preinstalled apps require tasks to run without user interaction and often before the end-user opens the app for the first time; such as a product survey app or a SMS server registration. Similarly, some apps will need servicing tasks to run without user interaction after an app has been updated. Preinstall and update tasks provide the mechanism for allowing tasks to run in the background without before the app is installed or when it is updated.          |
| [Exclusive apps](exclusive-apps.md)       | Learn how to set the OEM Store ID and SCM ID in the registry to enable exclusive apps for your devices.             |

## <a href="" id="developer-audience-heading"></a>Audience

Preinstalled and exclusive app guidance is designed for use by OEM and MO developers.
