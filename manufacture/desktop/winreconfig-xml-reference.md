---

Description: 'Learn how to create a WinREConfig.xml file for use with WinRE.'
ms.assetid: af2b402f-9a5c-4c6a-8852-61039e5bec2a
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'WinREConfig XML reference'

ms.date: 03/12/2018
ms.topic: article
ms.custom: RS5
---

# WinREConfig XML reference

This reference describes all xml elements that are used to author the winreconfig.xml file, which enables you to define custom support and diagnostic tools within WinRE.

## Example WinREConfig.xml file

```
<?xml version="1.0" encoding="utf-8"?>
<!-- WinREConfig.xml -->
<Recovery>
   <RecoveryTools>
      <RelativeFilePath>OEMDiagnostics.exe</RelativeFilePath>
      <CommandLineParam>/param1 /param2</CommandLineParam>
      <RequireLogonOnReset></RequireLogonOnReset>
   </RecoveryTools>
</Recovery>
```

## Description of available elements

| Element             | Description                                                                                                                                                                                                 |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RelativeFilePath    | The relative path from the \Tools subfolder of the folder in which Recenv.exe resides. For example, if Recenv.exe is located in X:\WinRE\, the path designated in this field is relative to X:\WinRE\tools. |
| CommandLineParam    | Optional parameters that are used when running the custom tool.                                                                                                                                             |
| RequireLogonOnReset | When present, "Reset this PC" -> "Remove everything" prompts users to choose an account and enter a password.                                                                                               |

## Create WinREConfig.xml

1. Create a tools subdirectory in your working Windows RE directory. For example, in `Sources\Recovery\Tools`.
2. Create an .xml file called winreconfig.xml.
3. Copy the following, and paste it into winreconfig.xml:
    
    ```XML
    <?xml version="1.0" encoding="utf-8"?>
    <!-- WinREConfig.xml -->
    <Recovery>
    <RecoveryTools>
        <RelativeFilePath></RelativeFilePath>
        <CommandLineParam></CommandLineParam>
        <RequireLogonOnReset></RequireLogonOnReset>
    </RecoveryTools>
    </Recovery>
    ```

4. Configure the elements in the xml file.
5. Save the file in your working Windows RE directory under `Sources\Recovery\Tools`.
