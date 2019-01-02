---

title: Merging packages using FeatureMerger
description: Merging packages using FeatureMerger
MSHAttr: 'PreferredLib:/library/windows/hardware'
ms.date: 11/02/2017
ms.topic: article


---

# Merging packages using FeatureMerger


The package feature merger tool (FeatureMerger.exe) combines packages
into a small, well-defined set of merged packages that adhere to a
predictable and consistent naming system. For retail images, OEMs must
use FeatureMerger.exe to merge their packages into a specific set of
packages that conform to the *Windows Standard Package Configuration*
(WSPC).

For an overview of package merging, see [Merging packages before imaging](merging-packages-before-imaging.md). For more information
about the WSPC requirements for retail images, see [Windows Standard Packaging Configuration (WSPC) requirements for retail images](packaging-requirements-for-retail-images.md).

## <span id="featuremerger.exe_overview"></span><span id="FEATUREMERGER.EXE_OVERVIEW"></span>FeatureMerger.exe overview


FeatureMerger.exe can be used in two ways: by passing a single feature
manifest XML file, or by passing an FMFileList XML file that describes
multiple feature manifests. The tool generates a set of merged packages
and a new feature manifest file that references the merged packages. The
new feature manifest file can be referenced in an OEMInput file that is
passed to ImgGen.cmd to build an image from the new merged packages.

To generate merged packages that comply with the (WSPC) for retail
images, you must organize all your packages into a single feature
manifest as described in [Windows Standard Packaging Configuration (WSPC) requirements for retail images](packaging-requirements-for-retail-images.md) and pass this
feature manifest to FeatureMerger.exe. If you are starting with packages
that are described in multiple feature manifest files, you can generate
merged packages that comply with WSPC in a multi-step process:

1.  Generate an initial set of merged packages and feature manifests by
    running FeatureMerger.exe with an FMFileList XML file that
    references the feature manifest files.

2.  Manually create a new feature manifest file that references all of
    the merged packages generated in the first step. Make sure that the
    merged packages are referenced in the WSPC-compliant sections of the
    feature manifest file, as described in [Windows Standard Packaging Configuration (WSPC) requirements for retail images](packaging-requirements-for-retail-images.md).

3.  Generate merged packages by running FeatureMerger.exe with the
    consolidated feature manifest file.

## <span id="using_featuremerger.exe_with_a_single_feature_manifest_xml_file"></span><span id="USING_FEATUREMERGER.EXE_WITH_A_SINGLE_FEATURE_MANIFEST_XML_FILE"></span>Using FeatureMerger.exe with a single feature manifest XML file


FeatureMerger.exe has the following syntax when used with a single
feature manifest XML file.

``` syntax
FeatureMerger InputFile OutputPackageDir OutputPackageVersion OutputFMDir /FMID:<feature manifest id> /Languages:<language identifier list>
/Resolutions:<resolution identifier list> /OwnerName:<owner name> /Variables:<variables> [/OwnerType:<owner type>] [/MergePackageRootReplacement:<replacement directory> 
[{+|-}Incremental] [{+|-}Compress] 
```

### <span id="Required_arguments_and_switches"></span><span id="required_arguments_and_switches"></span><span id="REQUIRED_ARGUMENTS_AND_SWITCHES"></span>Required arguments and switches

The following table lists the required arguments and switches when using
FeatureMerger.exe with a single feature manifest XML file.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Argument/switch</th>
<th>Description</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>InputFile</em></p></td>
<td><p>The path to the feature manifest XML file.</p></td>
<td><p>Text string</p></td>
</tr>
<tr class="even">
<td><p><em>OutputPackageDir</em></p></td>
<td><p>The path to the directory where the merged packages will be placed.</p></td>
<td><p>Text string</p></td>
</tr>
<tr class="odd">
<td><p><em>OutputPackageVersion</em></p></td>
<td><p>The version of the merged package that is created using the format &quot;&lt;major&gt;.&lt;minor&gt;.&lt;hotfix&gt;.&lt;build&gt;&quot;.</p>
<div class="alert">
<strong>Note</strong><br/><p>The package version must be incremented whenever a package is changed. For more info about package versioning and updates, see <a href="https://docs.microsoft.com/windows-hardware/service/mobile/update-requirements" data-raw-source="[Update requirements](https://docs.microsoft.com/windows-hardware/service/mobile/update-requirements)">Update requirements</a>.</p>
</div>
<div>

</div></td>
<td><p>Text string</p></td>
</tr>
<tr class="even">
<td><p><em>OutputFMDir</em></p></td>
<td><p>The path to the directory where the generated feature manifests will be placed. Feature manifests are generated with the same file name as the original feature manifest file name. The updated version of the feature manifest file contains the names of the merged packages and the provided version number.</p></td>
<td><p>Text string</p></td>
</tr>
<tr class="odd">
<td><p><strong>/FMID</strong>:<em>Feature manifest ID</em></p></td>
<td><p>A required short FM ID that describes the feature manifest file that is used in the merged package name to ensure that features from different FM files don&#39;t collide. The ID should be eight characters or less and be different from all other FM IDs. When generating merged packages for retail images, this ID must have the value of either <strong>Phone</strong> or <strong>Variant</strong>. For more info, see <a href="packaging-requirements-for-retail-images.md" data-raw-source="[Windows Standard Packaging Configuration (WSPC) requirements for retail images](packaging-requirements-for-retail-images.md)">Windows Standard Packaging Configuration (WSPC) requirements for retail images</a>.</p></td>
<td><p>Text string</p></td>
</tr>
<tr class="even">
<td><p><strong>/Languages</strong>:<em>Language identifier list</em></p></td>
<td><p>A semicolon “;” separated list of supported UI language identifiers. The following is an example of a language identifier list.</p>
<pre class="syntax" data-space="preserve"><code>en-us;de-de</code></pre></td>
<td><p>Text string</p></td>
</tr>
<tr class="odd">
<td><p><strong>/Resolutions</strong>:<em>Resolution identifier list</em></p></td>
<td><p>A semicolon “;” separated list of supported resolution identifiers. The following is an example of a resolutions identifier list.</p>
<pre class="syntax" data-space="preserve"><code>480x800;720x1280;768x1280;1080x1920</code></pre></td>
<td><p>Text string</p></td>
</tr>
<tr class="even">
<td><p><strong>/OwnerName</strong>:<em>Owner name</em></p></td>
<td><p>The name of the package owner, for example “Contoso”.</p></td>
<td><p>Text string</p></td>
</tr>
<tr class="odd">
<td><p><strong>/Variables</strong>:<em>variables</em></p></td>
<td><p>Additional variables that are used in the project file using the following syntax:&lt;name&gt;=&lt;value&gt;;&lt;name&gt;=&lt;value&gt;;</p>
<p>The following variables are pre-defined:</p>
<ul>
<li><p><strong>_cputype</strong>: Required. Specifies the CPU architecture. For Windows 10 Mobile, this variable must be set to &quot;arm&quot;.</p></li>
<li><p><strong>buildtype</strong>: Required. Specifies the build type. This variable must be set to either &quot;fre&quot; or &quot;chk&quot;.</p></li>
<li><p><strong>releasetype</strong>: Optional. Specifies the image release type. This variable can be set to either &quot;test&quot; or &quot;production&quot;. If this variable is not specified, the default value is &quot;test&quot;.</p></li>
</ul>
<p>For example, to set the CPU, build type, and release type, specify the variables like this:</p>
<pre class="syntax" data-space="preserve"><code>/Variables:_cputype=arm;buildtype=fre;releasetype:production</code></pre></td>
<td><p>Text string</p></td>
</tr>
</tbody>
</table>



### <span id="Optional_and_reserved_switches"></span><span id="optional_and_reserved_switches"></span><span id="OPTIONAL_AND_RESERVED_SWITCHES"></span>Optional and reserved switches

The following table lists the optional switches when using
FeatureMerger.exe with a single feature manifest XML file.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Switch</th>
<th>Description</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>/OwnerType</strong>:<em>Owner type</em></p></td>
<td><p>Specifies the resulting package owner type.</p></td>
<td><p>Text string – For OEM packages, this value must be set to &quot;OEM&quot;.</p></td>
</tr>
<tr class="even">
<td><p><strong>/MergePackageRootReplacement</strong>:<em>Replacement directory</em></p></td>
<td><p>Specifies a string to be used in the generated FM file for packages. Replaces the OutputPackageDir in the package paths.</p></td>
<td><p>Text string</p></td>
</tr>
<tr class="odd">
<td><p>{<strong>+</strong>|<strong>-</strong>}<strong>Incremental</strong></p></td>
<td><p>Specifies to only re-merge existing merged packages when one of the sources packages has changed. If this value is not set, the default is False. This means that all packages will be rebuilt each time FeatureMerger is called.</p></td>
<td><p>Boolean value: Precede this switch with either [+] to set to true or [-] to set to false</p></td>
</tr>
<tr class="even">
<td><p>{<strong>+</strong>|<strong>-</strong>}<strong>Compress</strong></p></td>
<td><p>This value allows for the compression of merged packages. When <strong>compress</strong> is true, the merge tool run time increases, but the package is optimized for storage size. This setting has no impact on imaging.</p></td>
<td><p>Boolean value: Precede this switch with either [+] to set to true or [-] to set to false</p></td>
</tr>
</tbody>
</table>



The following table lists the switches that are reserved for use by
Microsoft when using FeatureMerger.exe with a single feature manifest
XML file.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Switch</th>
<th>Description</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>/Critical</strong></p></td>
<td><p>Reserved for use by Microsoft.</p></td>
<td><p>Text string</p></td>
</tr>
</tbody>
</table>



### <span id="Examples"></span><span id="examples"></span><span id="EXAMPLES"></span>Examples

The following examples demonstrate FeatureMerger.exe syntax when specifying a feature manifest file.

``` syntax
FeatureMerger C:\FM\OEMSampleFM.xml D:\FM\MergedPackages 8.0.0.1 D:\FM\MergedFMs /FMID:Phone /Languages:en-us 
/Resolutions:480x800;720x1280;768x1280;1080x1920 /OwnerName:Contoso /variables:_cputype=arm;buildtype=fre
```

## <span id="using_featuremerger.exe_with_an_fmfilelist_xml_file"></span><span id="USING_FEATUREMERGER.EXE_WITH_AN_FMFILELIST_XML_FILE"></span>Using FeatureMerger.exe with an FMFileList XML file


FeatureMerger.exe has the following syntax when used with a single
feature manifest XML file.

``` syntax
FeatureMerger InputFile OutputPackageDir OutputPackageVersion OutputFMDir /InputFMDirPath:<path> /Variables:<variables> [/MergePackageRootReplacement:<replacement directory> 
[{+|-}Incremental] [{+|-}Compress] 
```

### <span id="Required_arguments_and_switches"></span><span id="required_arguments_and_switches"></span><span id="REQUIRED_ARGUMENTS_AND_SWITCHES"></span>Required arguments and switches

The following table lists the required arguments and switches when using
FeatureMerger.exe with an FMFileList XML file.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Argument/switch</th>
<th>Description</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>InputFile</em></p></td>
<td><p>The path to the FMFileList XML file. For more info about the contents of the FMFileList XML file, see <a href="#fmfilelist" data-raw-source="[Contents of the FMFileList XML file](#fmfilelist)">Contents of the FMFileList XML file</a> in this topic.</p></td>
<td><p>Text string</p></td>
</tr>
<tr class="even">
<td><p><em>OutputPackageDir</em></p></td>
<td><p>The path to the directory where the merged packages will be placed.</p></td>
<td><p>Text string</p></td>
</tr>
<tr class="odd">
<td><p><em>OutputPackageVersion</em></p></td>
<td><p>The version of the merged package that is created using the format &quot;&lt;major&gt;.&lt;minor&gt;.&lt;hotfix&gt;.&lt;build&gt;&quot;.</p>
<div class="alert">
<strong>Note</strong><br/><p>The package version must be incremented whenever a package is changed. For more info about package versioning and updates, see <a href="https://docs.microsoft.com/windows-hardware/service/mobile/update-requirements" data-raw-source="[Update requirements](https://docs.microsoft.com/windows-hardware/service/mobile/update-requirements)">Update requirements</a>.</p>
</div>
<div>

</div></td>
<td><p>Text string</p></td>
</tr>
<tr class="even">
<td><p><em>OutputFMDir</em></p></td>
<td><p>The path to the directory where the generated feature manifests will be placed. Feature manifests are generated with the same file name as the original feature manifest file name. The updated version of the feature manifest file contains the names of the merged packages and the provided version number.</p></td>
<td><p>Text string</p></td>
</tr>
<tr class="odd">
<td><p><strong>/InputFMDirpath</strong>:<em>path</em></p></td>
<td><p>The directory where the source feature manifest files are located.</p></td>
<td><p>Text string</p></td>
</tr>
<tr class="even">
<td><p><strong>/Variables</strong>:<em>variables</em></p></td>
<td><p>Additional variables used in the project file using the following syntax:&lt;name&gt;=&lt;value&gt;;&lt;name&gt;=&lt;value&gt;;</p>
<p>The following variables are pre-defined:</p>
<ul>
<li><p><strong>_cputype</strong>: Required. Specifies the CPU architecture. For Windows 10 Mobile, this variable must be set to &quot;arm&quot;.</p></li>
<li><p><strong>buildtype</strong>: Required. Specifies the build type. This variable must be set to either &quot;fre&quot; or &quot;chk&quot;.</p></li>
<li><p><strong>releasetype</strong>: Optional. Specifies the image release type. This variable can be set to either &quot;test&quot; or &quot;production&quot;. If this variable is not specified, the default value is &quot;test&quot;.</p></li>
</ul>
<p>For example, to set the CPU, build type, and release type, specify the variables like this:</p>
<pre class="syntax" data-space="preserve"><code>/Variables:_cputype=arm;buildtype=fre;releasetype:production</code></pre></td>
<td><p>Text string</p></td>
</tr>
</tbody>
</table>



### <span id="Optional_and_reserved_switches"></span><span id="optional_and_reserved_switches"></span><span id="OPTIONAL_AND_RESERVED_SWITCHES"></span>Optional and reserved switches

The following table lists the optional switches when using
FeatureMerger.exe with FMFileList XML file.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Switch</th>
<th>Description</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>/MergePackageRootReplacement</strong>:<em>Replacement directory</em></p></td>
<td><p>Specifies a string to be used in the generated feature manifest for packages. Replaces the OutputPackageDir in the package paths.</p></td>
<td><p>Text string</p></td>
</tr>
<tr class="even">
<td><p>{<strong>+</strong>|<strong>-</strong>}<strong>Incremental</strong></p></td>
<td><p>Specifies to only remerge existing merged packages when one of the sources packages has changed. If this value is not set, the default is False. This means that all packages will be rebuilt each time FeatureMerger.exe is called.</p></td>
<td><p>Boolean value: Precede this switch with either [+] to set to true or [-] to set to false</p></td>
</tr>
<tr class="odd">
<td><p>{<strong>+</strong>|<strong>-</strong>}<strong>Compress</strong></p></td>
<td><p>This value allows for the compression of merged packages. When <strong>compress</strong> is true, the merge tool run time increases, but the package is optimized for storage size. This setting has no impact on imaging.</p></td>
<td><p>Boolean value: Precede this switch with either [+] to set to true or [-] to set to false</p></td>
</tr>
</tbody>
</table>



The following table lists the switches that are reserved for use by
Microsoft when using FeatureMerger.exe with an FMFileList XML file.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Switch</th>
<th>Description</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>/Critical</strong></p></td>
<td><p>Reserved for use by Microsoft.</p></td>
<td><p>Text string</p></td>
</tr>
</tbody>
</table>



### <span id="Examples"></span><span id="examples"></span><span id="EXAMPLES"></span>Examples

The following example demonstrates FeatureMerger.exe syntax when
specifying an FMFileList XML file.

``` syntax
FeatureMerger.exe C:\FM\OEMSampleFMFileList.xml C:\FM\MergedPackages 8.0.0.1 C:\FM\MergedFMs  
/variables:_cputype=arm;buildtype=fre
```

### <span id="fmfilelist"></span><span id="FMFILELIST"></span>Contents of the FMFileList XML file

An FMFileList XML file contains the following elements.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Element</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FMs</strong></p></td>
<td><p>The <strong>FMs</strong> element contains one or more <strong>FM</strong> elements.</p></td>
</tr>
<tr class="even">
<td><p><strong>FM</strong></p></td>
<td><p>The <strong>FM</strong> element is used to point to feature manifest files.</p>
<pre class="syntax" data-space="preserve"><code>&lt;FM Path=&quot;C:\MyDir\OEMSampleFM.xml&quot; ReleaseType=&quot;Test&quot; OwnerType=&quot;OEM&quot; ID=&quot;Phone&quot; OwnerName=&quot;Contoso&quot; /&gt;</code></pre>
<p>The FM element has the following attributes.</p>
<ul>
<li><p><strong>Path</strong>: The path to the feature manifest files. The variable <strong>$(FMDirectory)</strong> can be used to specify the InputFMDir parameter in the path.</p></li>
<li><p><strong>ReleaseType</strong>: The release type must be set to either &quot;Test&quot; or &quot;Production&quot;. For FMs used in final retail images, this should be set to &quot;Production&quot;. In addition, all packages defined in a Production FM must have the ReleaseType set to &quot;Production&quot;. For more info about working with packages, see <a href="primary-elements-and-attributes-of-a-package-project-file.md" data-raw-source="[Primary elements and attributes of a package project file](primary-elements-and-attributes-of-a-package-project-file.md)">Primary elements and attributes of a package project file</a>.</p></li>
<li><p><strong>OwnerType</strong>: This value should be set to &quot;OEM&quot;.</p></li>
<li><p><strong>ID</strong>: A required short FM ID that describes the feature manifest file that is used in the merged package name to ensure that features from different FM files don&#39;t collide. The ID should be eight characters or less and be different from all other FM IDs. When generating merged packages for retail images, this ID must have the value of either <strong>Phone</strong> or <strong>Variant</strong>. For more info, see <a href="packaging-requirements-for-retail-images.md" data-raw-source="[Windows Standard Packaging Configuration (WSPC) requirements for retail images](packaging-requirements-for-retail-images.md)">Windows Standard Packaging Configuration (WSPC) requirements for retail images</a>.</p></li>
<li><p><strong>OwnerName</strong>: The owner name should be set to the OEM name, for example &quot;Contoso&quot;.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>SupportedResolutions</strong></p></td>
<td><p>The <strong>SupportedResolutions</strong> element is used to list the resolutions supported in the packages that will be merged.</p>
<pre class="syntax" data-space="preserve"><code>&lt;Resolution&gt;480x800&lt;/Resolution&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><strong>SupportedLanguages</strong></p></td>
<td><p>The <strong>SupportedLanguages</strong> element is used to list the languages supported in the packages that will be merged.</p>
<pre class="syntax" data-space="preserve"><code>&lt;Language&gt;en-US&lt;/Language&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><strong>SupportedLocales</strong></p></td>
<td><p>The <strong>SupportedLocales</strong> element is used to list the locales supported in the packages that will be merged.</p>
<pre class="syntax" data-space="preserve"><code>&lt;Locale&gt;en-US&lt;/Locale&gt;</code></pre></td>
</tr>
</tbody>
</table>



For example, the following sample file specifies two feature manifest
files, a list of supported resolutions, a supported language, and a
supported locale.

``` syntax
<?xml version="1.0" encoding="utf-8"?>
<FMCollectionManifest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
   xmlns:xsd="http://www.w3.org/2001/XMLSchema"
   xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate">

  <FMs>
    <FM Path="D:\FeatureMergeTest\OEMSampleFM1.xml" ReleaseType="Test" OwnerType="OEM" ID="FM1" OwnerName="Contoso"/>
    <FM Path="D:\FeatureMergeTest\OEMSampleFM2.xml" ReleaseType="Test" OwnerType="OEM" ID="FM2" OwnerName="Contoso"/>
  </FMs>
  <SupportedResolutions>
    <Resolution>480x800</Resolution>
    <Resolution>720x1280</Resolution>
    <Resolution>768x1280</Resolution>
  </SupportedResolutions>
  <SupportedLanguages>
    <Language>en-US</Language>
  </SupportedLanguages>
  <SupportedLocales>
    <Locale>en-US</Locale>
  </SupportedLocales>
</FMCollectionManifest>
```

## <span id="Paths_that_contain_spaces_"></span><span id="paths_that_contain_spaces_"></span><span id="PATHS_THAT_CONTAIN_SPACES_"></span>Paths that contain spaces


When you are using FeatureMerger.exe, be sure to use quotation marks
around paths that contain spaces. For example, if you define a
%WPDKCONTENTROOT% environment variable that is set to C:\\Program Files
(x86)\\Windows Kits\\10, the invocation of a package merger should be
enclosed in quotation marks:

`"%WPDKCONTENTROOT%\tools\bin\i386\FeatureMerger.exe"`

This guidance also applies to the parameters that take paths, such as
**/InputFMDirpath**.

## <span id="Package_code_signing"></span><span id="package_code_signing"></span><span id="PACKAGE_CODE_SIGNING"></span>Package code signing


Like all package generation, merged package generation uses catalog signing. For catalog signing to work, a certificate must be specified. 
To specify a signing certificate for package generation, follow the steps in [Set up the signing environment](https://msdn.microsoft.com/library/windows/hardware/dn756804) and [Sign binaries and packages](https://msdn.microsoft.com/library/windows/hardware/dn789217.aspx).

## <span id="related_topics"></span>Related topics


[Merging packages before imaging](merging-packages-before-imaging.md)


[Windows Standard Packaging Configuration (WSPC) requirements for retail images](packaging-requirements-for-retail-images.md)
