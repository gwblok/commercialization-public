---
title: Windows Mixed Reality HMD Exerciser Kit

description: The HMD Exerciser Kit automates validation of mixed reality (MR) head mounted displays (HMDs) and PCs.
keywords:
- HMD, testing
- head mounted display, testing
- HDMI USB testing 

ms.date: 1/10/2018
ms.topic: article


---

# Windows Mixed Reality HMD Exerciser Kit

The Windows Mixed Reality Head Mounted Display (MR HMD) Exerciser Kit is a hardware and software
package that automates the validation of MR HMDs and PCs. Key functions include HDMI and USB plug/unplug
testing, HMD display and audio monitoring, and user presence spoofing.
This document provides instructions and guidelines to create a best-in-class HMD.

The Windows Mixed Reality HMD Exerciser Kit consists of the following:

- HMD Exerciser
    - Arduino Compatible Main Board
    - Custom Hardware- Arduino Shields, Cables, and PCBs
- Software Tools and Libraries
- This Documentation

The Windows Mixed Reality HMD Exerciser Kit extends the [Microsoft USB
Test Tool (MUTT) Connection Exerciser](https://docs.microsoft.com/en-us/windows-hardware/drivers/usbcon/test-usb-type-c-systems-with-mutt-connex-c), so the documentation and tooling
might occasionally mention *Connection Exerciser* or *ConnEx*.

The Windows Mixed Reality HMD Exerciser Kit can be purchased through [MCCI](http://www.mcci.com/mcci-v5/devtools/exerciser-hmd.html).

## HMD Exerciser Overview

The HMD Exerciser consists of an Arduino-compatible base and three
stacked add-on boards called **Shields**. Together, these are referred
to as the **HMD Exerciser Main Board**. Alongside this is a separate
board designed to fit inside of the HMD. This board is referred to as
the **HMD Tester**.

Below is a simplified diagram of how the HMD Exerciser Main Board and
the HMD Tester connect to the HMD and the System Under Test:

![HMD Exerciser Kit Setup](images/image024.png)  

The HMD Exerciser Kit hardware enables the following functionality
out-of-the-box:

-  USB connect/disconnect and multiplexing
-  HDMI connect/disconnect and multiplexing
-  Display panel brightness and color monitoring for two displays
-  Audio level monitoring
-  User presence spoofing
-  HMD USB current and voltage monitoring
-  Dual servo control

The platform is also extensible, allowing new features through additional shields stacked on the HMD Exerciser Main Board.

