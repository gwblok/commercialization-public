---
title: OEM registration pages
description: Add your OEM registration pages to OOBE
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 01/25/2018
ms.topic: article


---
# OEM registration pages

You can customize OEM registration pages to gather customer information, and introduce offers, during OOBE. If you choose to implement the optional registration pages, we recommend that you use them to provide information and opportunities that benefit your customers. The Windows 10 OOBE is designed to maximize customer engagement by creating pages that focus on one thing at a time. As a result, OEM registration fields are divided between two separate pages.

Here is an example of the two OEM registration pages:

![OEM registration page 1](images/oem-registration-page1.png)

![OEM registration page 2](images/oem-registration-page2.png)

The OEM registration pages work with a Microsoft Account (MSA) to help customers enter in their information only once during OOBE. Microsoft prompts customers to sign up for an MSA or sign into an existing MSA during OOBE. When a customer does this, their first name, last name, and email address for the MSA, if provided, will be pre-filled in on registration page one. The customer can change their information before clicking **Next** if desired.

If the customer has not used an MSA, the fields on the OEM registration pages will be empty, and the customer can fill them in if and as desired.

The OEM registration pages are the last screens in the OOBE flow, after the user goes through all other steps in OOBE.

The customer information submitted through the registration pages will be stored in the `%systemroot%\System32\Oobe\Info\` folder, and will be encrypted using a public key that you place into the Windows image. Collect the encrypted data using a Microsoft Store app designated as your OEM App, or write a service that does this, and upload the data to your server. Decrypt the data using the corresponding private key once it's on your server.

## In this section

The following topics describe how to add your registration pages to OOBE.

| Topic                                     | Description                                                                        |
|:------------------------------------------|:-----------------------------------------------------------------------------------|
| [Design your registration pages](design-registration-pages.md)   | Guidance on customizing the registration page fields and HTML flyout pages. |
| [Configure OOBE.xml](registration-pages-oobexml.md)              | The elements of Oobe.xml are used to customize your registration pages. Create a custom Oobe.xml file or files as determined by the languages and regions where you ship your company's PCs. You can use multiple Oobe.xml files for language- and region-specific terms and settings so users see the correct language as soon as they start their PCs.                        |
| [Protect and collect user data](manage-user-data.md)               | To protect customer privacy, Windows encrypts the customer data that's created via the Registration pages using a public key that you generate and store in the Windows image. Create an OEM App or write a service that collects the encrypted data and uploads it to your server using SSL. You can then decrypt the data using the corresponding private key.   |
