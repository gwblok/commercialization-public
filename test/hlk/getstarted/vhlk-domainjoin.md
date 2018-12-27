---
title: VHLK - Domain Joining
description: Information and Guidance for Domain Joining the Windows Virtual Hardware Lab Kit (VHLK)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 10/02/2018
ms.topic: article
ms.custom: RS5
---

# Domain Joining the VHLK
This is a guide is to join the VHLK VM to a domain and add your domain username to the HLK datastores. Follow these steps after you have completed the setup guide. Joining the VHLK to a domain is completely optional, as the HLK will still work in a WORKGROUP configuration. However, joining to a domain gives the VM access to network resources.

## Joining a Domain
To domain-join the VHLK, follow the following steps:

1. Log in to your VHD as HLKAdminUser, password: Testpassword,1
2. Open up "Settings" and navigate to "System" 
3. Go to "About" in the left navigation and click "Join a domain" 
4. In the prompt, enter the domain you would like to join 
5. Enter your domain username and password to authorize joining the VHLK to the domain (if your company IT allows. Otherwise, request IT to authorize adding the VM to the domain)
6. Select "Administrator" in the drop-down menu 
7. Reboot the VHLK VM for the changes to take place.

## Check Network Settings After Domain Joining
After joining a domain, policy changes can be applied to your network settings. Verify that network discovery, and file sharing are turned on. 
1. Control Panel (icon view) -> Network and Sharing Center
2. Go to "Change advanced sharing settings"
3. On the current profile, set "Turn on network discovery", and "Turn on file and printer sharing"

When properly set up, the host system, virtual machine, and all client systems should be able to ping each other by **both IP address and name.**

## Add a Domain User to the HLK
This process requires that you have already followed the above steps for joining the VHD to the domain and rebooted the machine. Once domain-joined, log in as .\HLKAdminUser (password is "Testpassword,1"). You can use these steps to add your domain user to the HLK Manager to allow access to the HLK.

1. Open HLK Manager
2. Go to "Tools" in the top navigation and click "Management Console" 
3. Expand the datastore with the same name as the computer name and click "Users" 
4. Right-click on the "Users" or anywhere in the user list and click "New User..." 
5. Enter your "domain\username" in the top textbox and select "hlk_DSOwners" 
6. Now repeat steps 3-5 for the WTTIdentity datastore

Your domain user now has been successfully added to the HLK and you will have all the necessary permissions to access the HLK.
