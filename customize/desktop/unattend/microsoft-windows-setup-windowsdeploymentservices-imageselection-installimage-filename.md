---
title: Filename
description: Filename
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 29b9ad7c-b6d7-4c60-8832-dc6b0656ba01
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Filename


`Filename` specifies the file name of the image to be installed. This setting is optional. It is required only if more than one Windows image with the listed image name exists in the image group on the Windows Deployment Services server.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Filename</em></p></td>
<td><p>Specifies the file name of the image installed. <em>Filename</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [WindowsDeploymentServices](microsoft-windows-setup-windowsdeploymentservices.md) | [ImageSelection](microsoft-windows-setup-windowsdeploymentservices-imageselection.md) | [InstallImage](microsoft-windows-setup-windowsdeploymentservices-imageselection-installimage.md) | **Filename**

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
         <Filename>\\network_share\images\install-myimage.wim</Filename>
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

 

 







