---
description: For mobile retail images, OEM firmware packages (sometimes referred to as BSP submissions) must comply with the Windows Standard Package Configuration (WSPC).
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Windows Standard Packaging Configuration (WSPC) requirements for retail images
ms.assetid: d8b482d7-fc30-424a-9ce9-5aedf2dd5515

ms.date: 11/02/2017
ms.topic: article


---


# Windows Standard Packaging Configuration (WSPC) requirements for retail images


For mobile retail images, OEM firmware packages (sometimes referred to as BSP submissions) must comply with the Windows Standard Package
Configuration (WSPC).

WSPC is designed to achieve a better customer experience:

-   Smaller download sizes.
-   Reduced imaging and update errors.
-   Faster updates: Reduced system overhead needed to deliver and install updates.
-   Fewer updates: Device updates can make a "single hop" update from any image baseline.

**Note**  

Microsoft requires that all OEM retail firmware packages (BSP submissions) conform to the WSPC. While there are no exceptions to this policy, Microsoft has included tools and processes to ease the your transition to WSPC compliance.

 

## <span id="WSPC_overview"></span><span id="wspc_overview"></span><span id="WSPC_OVERVIEW"></span>WSPC overview


The purpose of WSPC is to define a firmware package set and update rules for that package set where it is easy to determine differences between any two arbitrary versions of the package set. The ability to easily and definitively determine the changes between any two package set versions allows Microsoft to use more efficient methods to update the device. The end result is a better customer experience as the user will experience only a single update session and associated reboot as opposed to several.

### <span id="Previous_WSPC_implementation"></span><span id="previous_wspc_implementation"></span><span id="PREVIOUS_WSPC_IMPLEMENTATION"></span>Previous WSPC implementation

Microsoft’s previous implementation of WSPC mandated a static firmware package set using static package names. The static package set and names applied globally to all of an OEM’s POPs. These packages were tightly coupled to the processor’s (SOC’s) the file system partition layout. While this implementation fulfilled the goal described in the summary above, it had two serious drawbacks. First, it put a high burden on you to achieve compliance due to its complex implementation. Second, the implementation’s tight coupling to the SOC’s file system partition layout does not accommodate new SOC’s with different partition configurations.

### <span id="New_WSPC_implementation"></span><span id="new_wspc_implementation"></span><span id="NEW_WSPC_IMPLEMENTATION"></span>New WSPC implementation

The new WSPC implementation based on a simpler generalization of our previous implementation. As long as we don’t remove or rename packages between firmware versions, determining the differences between any two arbitrary firmware versions is straight forward. We simply compare the source and target firmware package sets, and update any packages that have changed between the two. This includes the addition of packages from one firmware version to another.

Complying with the new model is simple and requires less overhead.
Instead of Microsoft prescribing the exact contents of the firmware package set, the you will do this by declaring one of your firmware package sets as a baseline. This baseline will apply to a specific set of POPs defined by the OEM. In addition, since this model is a generalized form of the previous WSPC implementation, Windows Phone 8.1 WSPC compliance firmware submissions are automatically compliant with the new WSPC implementation.

This implications of this model are:

1.  You can define multiple baselines on a per POP basis.

2.  Once a package is added to a firmware package set, it cannot be removed.

    If necessary, you must include an empty package.

3.  You cannot rename a package in a firmware package set.

    This is effectively the removal of an existing and the addition of a new package.

4.  You must be mindful to ensure the firmware package set does not grow beyond reasonable size.

    Feature merge should be used to manage firmware package set growth.

## <span id="WSPC_requirements"></span><span id="wspc_requirements"></span><span id="WSPC_REQUIREMENTS"></span>WSPC requirements


### <span id="Windows_Phone_Ingestion_Client"></span><span id="windows_phone_ingestion_client"></span><span id="WINDOWS_PHONE_INGESTION_CLIENT"></span>Windows Phone Ingestion Client

You must upgrade to the version x.x.x.x of the Windows Phone Ingestion Client (WPIC). There are breaking changes in this version that necessitate the upgrade, including:

1.  A **Baseline** parameter has been added to the
    [Initialize-FirmwareSubmission
    cmdlet](https://docs.microsoft.com/windows-hardware/service/mobile/initialize-firmwaresubmission-cmdlet). This will
    be used to identify a firmware submission as a baseline for WSPC compliance validation.
2.  The **nonWSPCCompliant** parameter of the [Initialize-FirmwareSubmission cmdlet](https://docs.microsoft.com/windows-hardware/service/mobile/initialize-firmwaresubmission-cmdlet) has been
    deprecated.
3.  All requests for all cmdlets from previous versions of the WPIC will be rejected with the following error:

    ``` syntax
    The Windows Phone Ingestion Client version you are using (Version {0}) is no longer supported.  Please make sure you are using the current version of the Windows Phone Ingestion Client, Version {1}.
    ```

### <span id="Feature_merge"></span><span id="feature_merge"></span><span id="FEATURE_MERGE"></span>Feature merge

Feature Merge continues to play a critical role in the new WSPC implementation. Packages must be feature merged to greatest extent possible to smallest resultant set possible. Feature Merging firmware packages will help manage package set growth as well avoid situations where you must work around deprecated packages for WSPC compliance.

More information on using feature merge can be found at the links below:

-   [Merging packages before imaging](merging-packages-before-imaging.md)
-   [Merging packages using FeatureMerger](merging-packages-using-featuremerger.md)

## <span id="Firmware_submissions"></span><span id="firmware_submissions"></span><span id="FIRMWARE_SUBMISSIONS"></span>Firmware submissions


Firmware updates are determined by comparing the baseline firmware submission with any subsequent submissions.

### <span id="Baseline_firmware_submission"></span><span id="baseline_firmware_submission"></span><span id="BASELINE_FIRMWARE_SUBMISSION"></span>Baseline firmware submission

To prepare a firmware submission for updating to retail devices by using a Request For Update (RFU), it must first be declared as a baseline. By declaring a firmware submission as a baseline, the package set comprising firmware submission will be used as the basis for WSPC compliance checks.

Prior to declaring a firmware submission as a baseline, you should have performed sufficient testing on the firmware so that they are confident that the package set will experience minimal and/or manageable variance in subsequent versions. Also, as discussed above, the package set should be feature merged to the greatest extent possible.

To declare the firmware submission as a baseline, you will run the [Initialize-FirmwareSubmission cmdlet](https://docs.microsoft.com/windows-hardware/service/mobile/initialize-firmwaresubmission-cmdlet) with the **baseline** parameter as shown below.

``` syntax
Initialize-FirmwareSubmission -TypeOfSubmission Image –UpdateHistoryPath [path] –OemInputPath [path] –OutputFilePath [path] -Baseline
```

### <span id="Subsequent_firmware_submissions"></span><span id="subsequent_firmware_submissions"></span><span id="SUBSEQUENT_FIRMWARE_SUBMISSIONS"></span>Subsequent firmware submissions

After a baseline firmware submission has been declared, subsequent firmware submissions targeting the same POPs will be compared with the previous baseline firmware version for WSPC compliance.

**Important**  Special care must be taken when targeting firmware submissions for multiple POPs with different baselines. Achieving WSPC compliance across **all baselines** can be difficult.

 

The WSPC compliance check will ensure that the package set of the new firmware version contains the same packages as the previous baseline or is a superset of the previous baseline. Consider the following package sets as an example:

**Baseline firmware submission**

Package1.spkg version 1

Package2.spkg version 1

Package3.spkg version 1

Package4.spkg version 1

**Firmware submission v2**

Package1.spkg version 2

Package2.spkg version 2

Package3.spkg version 2

Package4.spkg version 2

**Firmware submission v3**

Package1.spkg version 2

Package2.spkg version 2

Package3.spkg version 2

Package4.spkg version 2

Package5.spkg version 1

**Firmware submission v4**

Package1.spkg version 2

Package2.spkg version 2

Package3.spkg version 2

Package5.spkg version 1

Firmware submission v2 is WSPC-compliant with the baseline because the package set is the same between versions (even though the package versions are different).

Firmware submission v4 is not WSPC-compliant with the baseline because Package4.spkg does not exist (has been removed) in version 4.

Microsoft will process all firmware submissions regardless of their WSPC compliance status as long as you have not submitted it as a baseline.

``` syntax
Initialize-FirmwareSubmission -TypeOfSubmission Image –UpdateHistoryPath [path] –OemInputPath [path] –OutputFilePath [path]
```

If the new firmware submission is not WSPC-compliant, the following warning will be returned:

``` syntax
The firmware submission is not WSPC compliant with the baseline submission {1}.  This is because the packages {0} are missing from the new submission. Since this is not a new baseline, the firmware submission is allowed.  However, since this submission not WSPC compliant and is not a baseline, it will not be available for a retail servicing update.  Retail servicing updates are only allowed for the following scenarios: between an RTM source submission and an RTM target submission, or between a legacy non-WSPC compliant source submission and an RTM target submission.  To make this submission WSPC compliant, please ensure the missing packages are included in the submission.
```

Microsoft will reject baseline firmware submissions that are not WSPC-compliant. The following error will be shown:

``` syntax
<path>:\ Initialize-FirmwareSubmission -TypeOfSubmission Image –UpdateHistoryPath [path] –OemInputPath [path] –OutputFilePath [path] -Baseline

The firmware submission is not WSPC compliant with the baseline submission {1}.  This is because the packages {0} are missing from the new submission.  To make this submission WSPC compliant, please ensure the missing packages are included in the submission.
```

### <span id="_.SPKG_and__.CAB_firmware_package_names"></span><span id="_.spkg_and__.cab_firmware_package_names"></span><span id="_.SPKG_AND__.CAB_FIRMWARE_PACKAGE_NAMES"></span>\*.SPKG and \*.CAB firmware package names

Starting with Windows 10 Mobile, you’ll be able to build firmware using Microsoft’s Component Based Servicing Model (CBS). CBS packages use the \*.CAB extension where legacy Windows Phone packages use the \*.SPKG extension. Once pushed to the device, SPKG packages are converted to CAB packages on device so package names are not unique by extension.

As a result, when conducting WSPC compliance checks between firmware submissions, packages names differing only by SPKG or CAB extension will be treated as the same package.

For example, package1.spkg will be treated as the same package as package1.cab.

### <span id="Using_empty_packages_for_WSPC_compliance"></span><span id="using_empty_packages_for_wspc_compliance"></span><span id="USING_EMPTY_PACKAGES_FOR_WSPC_COMPLIANCE"></span>Using empty packages for WSPC compliance

In some cases, it may be necessary for a you to discontinue the use of a particular package that was part of a previous **baseline** submission.
However, to maintain WSPC compliance for subsequent **baseline** submissions, the deprecated package must continue to exist.

To support this scenario, you can submit an empty package of the same package name in the new baseline submission.

### <span id="Removal_packages"></span><span id="removal_packages"></span><span id="REMOVAL_PACKAGES"></span>Removal packages

Because the purpose of the new WSPC implementation is to remove the use of and need for removal packages, they are no longer supported for firmware submissions.

### <span id="Out_of_order_firmware_submissions"></span><span id="out_of_order_firmware_submissions"></span><span id="OUT_OF_ORDER_FIRMWARE_SUBMISSIONS"></span>Out of order firmware submissions

Over the course of a typical development lifecycle for firmware, we expect that the version number of new firmware will always be larger than the previous version number. However, we understand that there may be exceptions. As a result, Microsoft will also support cases where you submit firmware with versions that are less than the max firmware version submitted.

For example, assume the following baseline versions of firmware have
been submitted :

Baseline firmware submission v1

Baseline firmware submission v3

Baseline firmware submission v5

Baseline firmware submission v7

Now, you submit new firmware with version 4. WSPC compliance will need to run against:

-   Baseline firmware submission v3 to ensure that the v4 package set is a superset of the v3 package set (no removals between v3 and v5)
-   Baseline firmware submission v5 to ensure that the v5 package set is a superset of the v4 package set (no removals between v4 and v5)

If either of the checks fail and the firmware submission v4 was submitted without the **baseline** flag, the firmware will be accepted,
but the following warning will be returned:

``` syntax
<path>:\ Initialize-FirmwareSubmission -TypeOfSubmission Image –UpdateHistoryPath [path] –OemInputPath [path] –OutputFilePath [path] 

The firmware submission is not WSPC compliant with the baseline submission {1}.  This is because the packages {0} are missing from the new submission. Since this is not a new baseline, the firmware submission is allowed.  However, since this submission not WSPC compliant and is not a baseline, it will not be available for a retail servicing update.  Retail servicing updates are only allowed for the following scenarios: between an RTM source submission and an RTM target submission, or between a legacy non-WSPC compliant source submission and an RTM target submission.  To make this submission WSPC compliant, please ensure the missing packages are included in the submission. 
```

If either of the checks fail and the firmware submission v4 was submitted with the **baseline** parameter, the firmware will be rejected with the following error:

``` syntax
<path>:\ Initialize-FirmwareSubmission -TypeOfSubmission Image –UpdateHistoryPath [path] –OemInputPath [path] –OutputFilePath [path] -baseline

The firmware submission is not WSPC compliant with the baseline submission {1}.  This is because the packages {0} are missing from the new submission.  To make this submission WSPC compliant, please ensure the missing packages are included in the submission.
```

### <span id="Partial_submissions"></span><span id="partial_submissions"></span><span id="PARTIAL_SUBMISSIONS"></span>Partial submissions

Partial firmware submissions with the [Initialize-FirmwareSubmission
cmdlet](https://docs.microsoft.com/windows-hardware/service/mobile/initialize-firmwaresubmission-cmdlet) using the
**PartialImage** parameter will still be allowed, but the submission
must not be a baseline submission.

### <span id="NonWSPCCompliant_parameter"></span><span id="nonwspccompliant_parameter"></span><span id="NONWSPCCOMPLIANT_PARAMETER"></span>NonWSPCCompliant parameter

The **NonWspcCompliant** parameter is not supported.

For more info, see [Initialize-FirmwareSubmission
cmdlet](https://docs.microsoft.com/windows-hardware/service/mobile/initialize-firmwaresubmission-cmdlet).

### <span id="Request_for_update__RFU_"></span><span id="request_for_update__rfu_"></span><span id="REQUEST_FOR_UPDATE__RFU_"></span>Request for update (RFU)

As we mentioned previously, retail servicing must be between baseline firmware submissions. By retail servicing, we mean using the
[New-RequestForUpdate cmdlet](https://docs.microsoft.com/windows-hardware/service/mobile/new-requestforupdate-cmdlet) with the retail servicing type. Example is shown below:

``` syntax
$result = New-RequestForUpdate 
-FirmwareSubmissionTicketId <Target Firmware Submission> 
–RequestForUpdateType RetailServicing 
-SourceFirmwareSubmissionTicketId <Source Firmware Submission> 
-OemDeviceName xxx 
-MOId 000-yy
```

RFUs used for retail servicing must be:

-   Between two successful baseline firmware submissions
-   The version of the target firmware submission must be greater than the source firmware submission

If the target firmware submissions is not a baseline, the request will be rejected and the following error will be shown:

``` syntax
The target firmware submission is not a Baseline submission, which is required for a retail servicing update. A retail servicing update is only allowed for the following scenarios: between a Baseline source submission and a Baseline target submission, or between a legacy non-WSPC compliant source submission and a Baseline target submission. Please also make sure you are using the current version of the Windows Phone Ingestion Client, Version {0}.  Submission status in this request for update: [Target submission: {1}, {2}], [Source submission: {3}, {4}].
```

If neither the source nor target firmware submissions are baseline but the source firmware submission is WSPC compliant, the request will be
rejected and the following error will be shown:

``` syntax
The source firmware submission is WSPC compliant, however it is not a Baseline submission, which is required for a retail servicing update. A retail servicing update is only allowed for the following scenarios: between a Baseline source submission and a Baseline target submission, or between a legacy non-WSPC compliant source submission and a Baseline target submission.  Please also make sure you are using the current version of the Windows Phone Ingestion Client, Version {0}.
```

If the target firmware submissions is not a baseline, but the request is not for retail servicing, the request will be accepted and processed
with a warning similar to the following:

``` syntax
$result = New-RequestForUpdate 
-FirmwareSubmissionTicketId <Target Firmware Submission> 
–RequestForUpdateType Trial
-SourceFirmwareSubmissionTicketId <Source Firmware Submission> 
-OemDeviceName xxx 
-MOId 000-yy

The target firmware submission is not a Baseline submission, which is required for a retail servicing update. A retail servicing update is only allowed for the following scenarios: between a Baseline source submission and a Baseline target submission, or between a legacy non-WSPC compliant source submission and a Baseline target submission. Since this is a non-retail RFU, it is being allowed, however the RFU should be made WSPC compliant before submitting the retail RFU. RFU status in this request for update: [Target submission: {0}, {1}], [Source submission: {2}, {3}].
```

If neither the source nor target firmware submissions are baseline but the source firmware submission is WSPC compliant, but the request is not for retail servicing, the request will be accepted and processed with a warning similar to the follow:

``` syntax
The source firmware submission is WSPC compliant, however it is not a Baseline submission, which is required for a retail servicing update. A retail servicing update is only allowed for the following scenarios: between a Baseline source submission and a Baseline target submission, or between a legacy non-WSPC compliant source submission and a Baseline target submission. Since this is a non-retail RFU, it is being allowed, however the RFU should be made WSPC compliant before submitting the retail RFU.
```

## <span id="Support_for_legacy_WSPC_compliance"></span><span id="support_for_legacy_wspc_compliance"></span><span id="SUPPORT_FOR_LEGACY_WSPC_COMPLIANCE"></span>Support for legacy WSPC compliance


Because the new WSPC compliance is a more general implementation of the previous WSPC model, legacy WSPC compliant submissions will
automatically be compliant with the new model.

All existing WSPC submissions will automatically be marked as baseline as part of the rollout of this change.

## <span id="Migrating_from_a_legacy_non-compliant_submission"></span><span id="migrating_from_a_legacy_non-compliant_submission"></span><span id="MIGRATING_FROM_A_LEGACY_NON-COMPLIANT_SUBMISSION"></span>Migrating from a legacy non-compliant submission


Because our customers already have devices already with non-WSPC compliant firmware, Microsoft will provide an upgrade path for these
devices to WSPC-compliant versions.

To accommodate this, Microsoft will allow retail servicing from non baseline (non-WSPC compliant) firmware submissions to baseline firmware
submissions provided the following conditions are met:

-   The source firmware submission version is less than the minimum version of the baseline firmware version.
-   The baseline target firmware submission is WSPC-compliant with the source firmware submission.

The implication of these conditions is that the package set of the existing source non-compliant submissions will effectively become the baseline package set for WSPC compliance going forward.

For more info, see [New-RequestForUpdate
cmdlet](https://docs.microsoft.com/windows-hardware/service/mobile/new-requestforupdate-cmdlet).

## <span id="Tools"></span><span id="tools"></span><span id="TOOLS"></span>Tools


The Microsoft Windows Phone Ingestion Client (WPIC) and Phone Image Inspector (ImgVal) have both been updated to determine if firmware submissions are WSPC-compliant or not. However, because WSPC compliance is now determined by comparison to previously submitted baseline firmware, both tools must have access to Microsoft’s UTS systems. As a result, ImgVal will not be capable of running in a standalone mode.
During installation, ImgVal will prompt you for your Microsoft Connect credentials as it does currently for WPIC. For more info about WPIC, see [Ingestion Client for Windows Phone](https://docs.microsoft.com/windows-hardware/service/mobile/ingestion-client-for-windows-phone).

### <span id="Standard_validation"></span><span id="standard_validation"></span><span id="STANDARD_VALIDATION"></span>Standard validation

In addition to WSPC validation, WPIC and ImgVal will also run a new set of standard validations against firmware submissions. These standard validation rules are designed to catch common errors in firmware submissions that may cause issues during retail servicing.

Previously, this validation was bypassed for NonWspcCompliant submissions. Going forward they will be applied to all submissions.
Standard validation errors are blocking and must be fixed for successful firmware submissions.

The standard validation rules are listed below:

|     | Validation                  | Rule                                                                                      |
|-----|-----------------------------|-------------------------------------------------------------------------------------------|
| 1   | Removal packages            | Removal packages are not allowed. This includes SPKRs or CBS-Rs.                          |
| 2   | Package version             | Packages cannot have a 0.0.0.0 package version.                                           |
| 3   | Binary packages in MainOS   | Packages in MainOS partition cannot be flagged as binary partition package.               |
| 4   | Binary packages in EFIESP   | Packages in EFIESP partition cannot be flagged as binary partition package.               |
| 5   | Binary packages in UpdateOS | Packages in UpdateOS partition cannot be flagged as binary partition package.             |
| 6   | PhoneFirmwareRevision       | Firmware version must be in x.x.x.x format where x is between 0 and 65535 (inclusive).    |
| 7   | PhoneManufacturer           | Phone manufacturer name must be alphanumerical and less than or equal to 32 characters.   |
| 8   | PhoneManufacturerModelName  | OEM device name must be alphanumerical with -.\_ and less than or equal to 32 characters. |
| 9   | PhoneMobileOperatorName     | Mobile operator name must conform to XXX-XX format.                                       |

 

**Note**  Firmware created through the Qualcomm Windows Phone Customization Tool (QWPCT) will automatically conform to the standard
compliance rules above.

 

### <span id="merged"></span><span id="MERGED"></span>Building merged packages

To conform to WSPC, OEMs should use FeatureMerger.exe to reduce the total number of packages in a firmware submissions to the greatest extent possible. For more info about the package merging process and how the merged package names are derived, see [Merging packages before imaging](merging-packages-before-imaging.md).

### <span id="empty"></span><span id="EMPTY"></span>Creating empty packages

Achieving WSPC compliance for a new firmware submission requires that it contain a superset of the packages contained in the previous baseline submission. An impact of this WSPC compliance rule is that packages may not be removed from new firmware submissions as compared to the previous baseline.

In some cases, it may be necessary to reconfigure your firmware in such a way that a package in the previous baseline is no longer used. In order to achieve WSPC compliance in this case, you will need to create and include an empty package in the firmware.

The following steps summarize the process of creating an empty feature merged package called Contoso.BASE.MainOS.spkg:

1.  Build one empty package for the partition targeted by the package using PkgGen.exe. Ensure the &lt;Components&gt; element is empty. For example, the following package XML generates an empty project for the MainOS partition.

    ``` syntax
    <Package xmlns="urn:Microsoft.WindowsPhone/PackageSchema.v8.00"
       Owner="Contoso" OwnerType="OEM" Component="EmptyPackage" SubComponent=”ForMainOS”  ReleaseType="Production" Platform="<PLAT>" Partition="MainOS">
       <Components>
       </Components>
    </Package>
    ```

2.  Reference the empty packages in the feature manifest. For example, the following feature manifest generates merged base packages and
    includes a combination of empty packages for the MainOS partition.

    ``` syntax
    <FeatureManifest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate">
      <BasePackages>
      <PackageFile Path="C:\Packages" Name="Contoso.BASE.MainOS.spkg" Partition="MainOS" />
        <PackageFile Path="C:\EmptyPackage" Name="Contoso.EmptyPackage.ForMainOS.spkg"/>
        <PackageFile Path="C:\EmptyPackage" Name="Contoso.EmptyPackage.ForMainOS2.spkg"/>
        <PackageFile Path="C:\EmptyPackage" Name="Contoso.EmptyPackage.ForMainOS3.spkg"/>
      </BasePackages>
    </FeatureManifest>
    ```

3.  Generate merged packages by running FeatureMerger.exe with the feature manifests that reference the empty packages. The generated
    merged packages will contain both the empty packages and, where applicable, packages with content from the OEM.

Alternately, you can generate an empty package for the partition targeted by the package using PkgGen.exe without using feature merge.  Ensure the &lt;component&gt; element is empty. For example, the following package XML generates an empty project for the MainOS partition called Contoso.BASE.MainOS.spkg.

``` syntax
<Package xmlns="urn:Microsoft.WindowsPhone/PackageSchema.v8.00"
   Owner="Contoso" OwnerType="OEM" Component="BASE" SubComponent=”MainOS”  ReleaseType="Production" Platform="<Plat>" Partition="MainOS">
   <Components>
   </Components>
</Package>
```

## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Activity</th>
<th>Message</th>
<th>Resolution</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>Any WPIC command</td>
<td>The Windows Phone Ingestion Client version you are using (Version {0}) is no longer supported. Please make sure you are using the current version of the Windows Phone Ingestion Client, Version {1}.</td>
<td>Download and install the latest Windows Phone Ingestion Client from <a href="https://connect.microsoft.com" data-raw-source="[Microsoft Connect](https://connect.microsoft.com)">Microsoft Connect</a>.</td>
</tr>
<tr class="even">
<td>2</td>
<td>Request for update</td>
<td>WSPC compliant with the baseline submission {1}. This is because the packages {0} are missing from the new submission. Since this is not a new baseline, the firmware submission is allowed. However, since this submission not WSPC compliant and is not a baseline, it will not be available for a retail servicing update. Retail servicing updates are only allowed for the following scenarios: between an RTM source submission and an RTM target submission, or between a legacy non-WSPC compliant source submission and an RTM target submission. To make this submission WSPC-compliant, please ensure the missing packages are included in the submission.</td>
<td><p>No action is necessary if this firmware version is not going to be used for a retail update.</p>
<p>However, Microsoft recommends that all new firmware submission be WSPC-compliant with the previous baseline.</p>
<p>To fix the WSPC compliance issue, ensure the missing package (or empty package as appropriate) is included in the submission.</p></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Request for update</td>
<td>The firmware submission is not WSPC-compliant with the baseline submission {1}. This is because the packages {0} are missing from the new submission. To make this submission WSPC-compliant, please ensure the missing packages are included in the submission.</td>
<td><p>Since this submission is a baseline, it must be WSPC-compliant with the previous baseline.</p>
<p>Ensure the missing package (or empty package as appropriate) is included in the submission.</p></td>
</tr>
<tr class="even">
<td>4</td>
<td>Firmware submission</td>
<td>To be WSPC-compliant, you cannot remove a package. The following packages were removed &#39;{0}&#39;.</td>
<td>Ensure the missing package (or empty package as appropriate) is included in the submission to be WSP-compliant.</td>
</tr>
<tr class="odd">
<td>5</td>
<td>Firmware submission</td>
<td>Using a cached package list for validation because a connection to the server cannot be established. &#39;{0}&#39;</td>
<td>Ensure the Image Validation tool or Windows Phone Ingestion Client have access to Microsoft’s code signing and publishing systems.</td>
</tr>
<tr class="even">
<td>6</td>
<td>Firmware submission</td>
<td>Could not retrieve the baseline package list while running on the client. A WSPC compliance check cannot be performed.</td>
<td>A check will be performed on the server. If error persists, contact Microsoft.</td>
</tr>
<tr class="odd">
<td>7</td>
<td>Firmware submission</td>
<td>Could not retrieve the baseline package list while running on a Windows server. A WSPC compliance check cannot be performed.</td>
<td>Contact Microsoft.</td>
</tr>
<tr class="even">
<td>8</td>
<td>Firmware submission</td>
<td>An exception was thrown while loading a package. {0} : {1}</td>
<td>Contact Microsoft.</td>
</tr>
<tr class="odd">
<td>9</td>
<td>Firmware submission</td>
<td>Could not retrieve the firmware version of the submission.</td>
<td>Contact Microsoft.</td>
</tr>
<tr class="even">
<td>10</td>
<td>Firmware submission</td>
<td>There was an incorrect number of baseline submissions returned. Count: {0}</td>
<td>Contact Microsoft.</td>
</tr>
<tr class="odd">
<td>11</td>
<td>Firmware submission</td>
<td>No submission results were returned so a cached copy is being used.</td>
<td>Ensure the Image Validation tool or Windows Phone Ingestion Client have access to Microsoft’s code signing and publishing systems.</td>
</tr>
<tr class="even">
<td>12</td>
<td>Firmware submission</td>
<td>The following variant is not WSPC compliant. OEM: {0}, Mobile operator: {1}, OEM device name: {2}.</td>
<td>Ensure the firmware submission is targeting the correct variants. Also check the previous baseline for the offending variant and ensure all packages are present in the new submission.</td>
</tr>
<tr class="odd">
<td>13</td>
<td>Firmware submission</td>
<td>Could not get baseline package lists online for validation because connection to server cannot be established. Error: &#39;{0}&#39;</td>
<td>Ensure the Image Validation tool or Windows Phone Ingestion Client have access to Microsoft’s code signing and publishing systems.</td>
</tr>
<tr class="even">
<td>14</td>
<td>Firmware submission</td>
<td>No baseline submission result returned, this must be the first and new baseline submission for this POP.</td>
<td>No baseline submission result returned, this must be the first and new baseline submission for this POP. If first baseline submission, this is the correct behavior. Otherwise ensure the firmware submission is targeting the correct variants.</td>
</tr>
<tr class="odd">
<td>15</td>
<td>Firmware submission</td>
<td>Could not retrieve the latest baseline package list through partner service. Client local cache is used instead.</td>
<td>Ensure the Image Validation tool or Windows Phone Ingestion Client have access to Microsoft’s code signing and publishing systems.</td>
</tr>
</tbody>
</table>

 

## <span id="related_topics"></span>Related topics

[Merging packages before imaging](merging-packages-before-imaging.md)

[Merging packages using FeatureMerger](merging-packages-using-featuremerger.md)

