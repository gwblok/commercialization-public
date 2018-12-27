---
title: Partner Guide to WSSD Certification
description: Partner Guide to WSSD Certification
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ABAA7069-52C3-4188-9246-6504146459EC


ms.date: 10/11/2018
ms.topic: article


---

# Partner Guide to WSSD Certification


## <span id="Introduction"></span><span id="introduction"></span><span id="INTRODUCTION"></span>Introduction


Windows Server 2016 offers a range of competitive and differentiated capabilities to enable lower-cost, cloud scale Software-Defined Datacenter (SDDC) scenarios. The goal of the Windows Server Software-Defined (WSSD) program is to ensure that customers have a seamless deployment and steady-state operational experience on validated hardware. To that end, the WSSD program will provide guidance around four distinct technical stages:

-   **Design**: Reference architecture for configuration selection, design principles, and best practices
-   **Validate**: Additional SDDC tests to ensure components and systems meet WSSD requirements
-   **Deploy**: Initial deployment guidance with experience guides and scripts for automation
-   **Operate**: Experience guides for steady-state operational management using System Center Virtual Machine Manager (VMM) and System Center Operations Manager (OM)

This topic focuses on the guidance required to complete WSSD Certification as part of the Validate stage above.

## Audience
This topic is for WSSD Solution Vendors and OEMs and is not intended to provide specific guidance for IHVs or those doing individual component-level certification (i.e. SDDC AQs).
## Overview of Windows Server software-defined offerings

WSSD provides three offerings:
1. Hyper-converged Infrastructure (HCI) Standard - Combines compute and storage in the same cluster of server nodes to provide a highly-virtualized solution that's easy to deploy, manage, and scale. This deployment option simplifies IT infrastructure since customers no longer need traditional IT silos of compute, shared storage (SAN/NAS), and networking. It's best suited for small to mid-sized IT environment running virtualized (Hyper-V) workloads.
2. Converged Software-Defined Storage (SDS) - Provides a lower cost, enterprise-grade, shared storage alternative to traditional SAN/NAS. Built using a cluster of server nodes, it's easy to deploy, manage, and scale out to build storage capacity as customer's needs grow over time. On one hand, its simplicity and low cost would appeal to small/mid-sized IT environments, it's scale, flexibility, and cloud-scale traits would benefit large service providers and enterprise IT. Any workloads that are compatible with SMB storage are a good fit for this offer.
3. Hyper-converged Infrastructure (HCI) Premium - Provides a comprehensive software-defined "datacenter in a box". Building on the same foundation as HCI-Standard, these offers add Software-Defined Networking (SDN) and Assurance to the stack. These offerings provide the perfect building blocks for customers - typically a large enterprise, service provider or hoster - that want to build on premise SDDC that emulates large public clouds like Azure. While SDN provides the benefit to deploy, provision and manage networking services at scale, Assurance provides essential tenant isolation and services for running a secure on-premises multi-tenant cloud.