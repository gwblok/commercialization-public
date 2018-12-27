---
title: ImageGroup
description: ImageGroup
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 46d49fa0-2cc5-4243-9948-e01a4a7605ad
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ImageGroup


`ImageGroup` specifies the Windows Deployment Services image group of the image to be installed.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Image_group_name</em></p></td>
<td><p>Specifies the image group of the image to be installed. <em>Image_group_name</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [WindowsDeploymentServices](microsoft-windows-setup-windowsdeploymentservices.md) | [ImageSelection](microsoft-windows-setup-windowsdeploymentservices-imageselection.md) | [InstallImage](microsoft-windows-setup-windowsdeploymentservices-imageselection-installimage.md) | **ImageGroup**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows a complete Windows Deployment Services deployment.

```
<WindowsDeploymentServices>
   <Login>
      <WillShowUI>OnError</WillShowUI>
      <Credentials>
         <Username>Administrator</Username>
         <Domain>MY-DOMAIN-NAME</Domain>
         <Password>********</Password>
      </Credentials>
   </Login>
  <ImageSelection>
      <WillShowUI>OnError</WillShowUI>
      <InstallImage>
         <ImageName>MY_IMAGE_NAME</ImageName>
         <ImageGroup>My IMAGE GROUP</ImageGroup>
      </InstallImage>
      <InstallTo>
         <DiskID>0</DiskID>
         <PartitionID>1</PartitionID>
      </InstallTo>
   </ImageSelection>
</WindowsDeploymentServices>
<DiskConfiguration>
   <WillShowUI>OnError</WillShowUI>
   <Disk>
      <DiskID>0</DiskID>
      <WillWipeDisk>false</WillWipeDisk>
      <ModifyPartitions>
         <ModifyPartition>
            <Order>1</Order>
            <PartitionID>3</PartitionID>
            <Letter>C</Letter>
            <Label>TestOS</Label>
            <Format>NTFS</Format>
            <Active>true</Active>
            <Extend>false</Extend>
         </ModifyPartition>
      </ModifyPartitions>
   </Disk>
</DiskConfiguration>
```

## Related topics


[InstallImage](microsoft-windows-setup-windowsdeploymentservices-imageselection-installimage.md)

 

 







