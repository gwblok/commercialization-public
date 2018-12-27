---

Description: Customize the Start Screen
ms.assetid: b28584ec-487e-4b59-a7f6-deb797d464a8
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Customize the Start Screen

redirect_url: https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/customize-start-layout
ms.date: 05/02/2017
ms.topic: article


---

# Customize the Start Screen


You can add your business apps to a Windows image and customize the **Start** screen to include them. You can customize the **Start** screen for Windows 10 Enterprise, Windows Server 2016, or a domain-joined PC running Windows 10 Pro.

Line-of-business (LOB) Microsoft Store apps do not have to be certified or installed through the Microsoft Store. Adding apps that do not come from the Microsoft Store is called *sideloading*. Sideloaded apps must be signed with a certificate that is chained to a trusted root certificate. For more information about sideloading Microsoft Store apps, including requirements, see [Sideload Apps with DISM](sideload-apps-with-dism-s14.md).

To install Microsoft Store apps that are not part of your business line, you must use the Microsoft Store.

## <span id="BKMK_layoutmodificationxml"></span> Use LayoutModification XML

You can customize the Windows 10 Start menu by using layoutmodification.xml to modify or replace the default Start layout and its tiles. To see how to use layoutmodification.xml, see [Start layout XML for desktop editions of Windows 10](https://docs.microsoft.com/en-us/windows/configuration/start-layout-xml-desktop).


## <span id="BKMK_StartTiles"></span><span id="bkmk_starttiles"></span><span id="BKMK_STARTTILES"></span>Use StartTiles settings to lay out the Start screen

> [!IMPORTANT]
> Customizing the Start menu using StartTiles in unattend is deprecated. Use layoutmodification.xml to customize the Windows 10 Start menu.

You can use settings in an unattended answer file to specify how the app tiles display on the **Start** screen. You can’t remove tiles from the **Start** screen or label groups using unattend settings, but you can specify how tiles for 24 installed apps are displayed using the StartTiles settings. Each of the settings maps to a fixed position in the **Start** screen templates, and these positions vary according to the destination PC's screen size, resolution, and DPI. Each setting specifies whether the tile is a wide tile or a square tile for an app, or if it's a square tile for a desktop app.

1.  Get the AppID of your LOB apps.

    To use the unattend settings, you need the specific AppID string that is associated with an installed app. You can create this string by using the get-AppxPackage cmdlet in Windows PowerShell. The following example shows how to get the AppID string to use in the unattend settings for every app that is already installed on the computer:

    ```
    $installedapps = get-AppxPackage
    foreach ($app in $installedapps)
    {
        foreach ($id in (Get-AppxPackageManifest $app).package.applications.application.id)
        {
            $app.packagefamilyname + "!" + $id
        }
    }
    ```

2.  Open an answer file.

    Create or open an answer file in Windows System Image Manager (Windows SIM). For more information, see [Windows System Image Manager Technical Reference](https://msdn.microsoft.com/library/windows/hardware/dn922445).

3.  Add StartTiles settings to your answer file.

    Use the Microsoft-Windows-Shell-Setup | StartTiles | &lt;tileSetting&gt; setting to specify the AppID of the app whose tile should appear in a particular position on the **Start** screen by default. The tile settings follow three naming patterns:

    -   WideTile and a number from 01 to 06.

        Each app that you specify for these settings must provide assets, in the app manifest, that provide a wide tile. Each app setting requires that you input the AppID.

    -   SquareTile and a number from 01 to 12.

        Each app setting requires that you input the AppID.

    -   DesktopOrSquareTile and a number from 01 to 06.

        For apps in any or all of the DesktopOrSquare settings, you need to specify the appID for the corresponding app, or the path to the desktop app.

    **Note**  If you put an app that supports wide tiles in a square tile spot, the tile is forced to be square instead of wide.

    If you skip a setting, Windows rearranges the flow of app tiles around the app tile position of that setting on the **Start** screen.

4.  Deploy your Windows image using the modified answer file.

    For more information, see [Deploy a Custom Image](deploy-a-custom-image.md).

For more information about these settings, see the StartTiles settings topics in the Microsoft-Windows-Shell-Setup component in the [Windows Unattended Setup Reference](http://go.microsoft.com/fwlink/?LinkId=206281) on TechNet.

## <span id="related_topics"></span>Related topics


[Sideload Apps with DISM](sideload-apps-with-dism-s14.md)

[Mount and Modify a Windows Image Using DISM](mount-and-modify-a-windows-image-using-dism.md)

[Deployment Imaging Servicing Management (DISM) Cmdlets in Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=239926)

 

 






