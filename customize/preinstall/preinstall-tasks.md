---
title: Preinstall tasks
description: OEMs and MOs are permitted to ship preinstalled apps in the device image.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: CE7CF98C-AA85-45FF-890D-5049AE0A7152


ms.date: 05/02/2017
ms.topic: article


---
# Preinstall tasks

OEMs and MOs are permitted to ship preinstalled apps in the device image. Some of those preinstalled apps require tasks to run without user interaction and often before the end-user opens the app for the first time; such as a product survey app or a SMS server registration. Similarly, some apps will need servicing tasks to run without user interaction after an app has been updated. Preinstall and update tasks provide the mechanism for allowing tasks to run in the background without before the app is installed or when it is updated.

There are two deployments task types available to UAPs: PreInstallConfigTask and UpdateTask. Both are IBackgroundTasks.

Here are the general rules that govern these tasks.

* Your app manifest can contain only one PreInstallConfigTask and one UpdateTask.
* Deployment tasks are applicable to any platform type.
* Deployment tasks can execute after the deployment operation has been completed and committed.
* Failed deployment tasks are not restarted.
* Failed deployment tasks do not affect the successful deployment of the app.
* Deployment tasks are not restarted after reboot.
* Deployment tasks should not depend on one another.

## Code Examples

### UpdateTask example

Update task is supported for any possible update path, for example:

* .xap to .xap
* .xap to .appx
* .xap to .appxbundle
* .appx to .appx
* .appx to .appxbundle
* .appxbundle to .appxbundle

Here’s the example .appx manifest:

```xml
<Package>
  <Extensions>
    <Extension Category="windows.activatableClass.inProcessServer">
      <InProcessServer>
        <Path>App.dll</Path>
        <ActivatableClass ActivatableClassId="App.UpdateTask" ThreadingModel="MTA"/>
      </InProcessServer>
    </Extension>
  </Extensions>

  <Applications>
    <Application>
      <Extensions>
        <Extension Category="windows.updateTask"  EntryPoint="App.UpdateTask">
        </Extension>
      </Extensions>
    </Application>
  </Applications>
</Package>
```

Here’s the example C\# code:

```c#
public sealed class UpdateTask : IBackgroundTask
{
    public async void Run(IBackgroundTaskInstance taskInstance)
    {
        CancellationTokenSource cts = new CancellationTokenSource();
        var deferral = taskInstance.GetDeferral();
        taskInstance.Canceled +=
            (sender, reason) =>
            {
                cts.Cancel();
            };
        try
        {
            await MigrateApp(); // Do app migration/update steps.
        }
        catch (TaskCanceledException x)
        {
            // do nothing on cancelation.
        }
        deferral.Complete();
    }
}
```

### PreInstallConfigTask task example

Here’s the example .appx manifest:

```xml
<Package>
  <Extensions>
    <Extension Category="windows.activatableClass.inProcessServer">
      <InProcessServer>
        <Path>App.dll</Path>
        <ActivatableClass ActivatableClassId="App.PreInstallConfigTask" ThreadingModel="MTA"/>
      </InProcessServer>
    </Extension>
  </Extensions>

  <Applications>
    <Application>
      <Extensions>
        <Extension Category="windows.preInstalledConfigTask"  EntryPoint=" App.PreInstallConfigTask">
        </Extension>
      </Extensions>
    </Application>
  </Applications>
</Package>
```

Here’s the example C\# code:

```c#
public sealed class PreInstallConfigTask : IBackgroundTask
{
    public async void Run(IBackgroundTaskInstance taskInstance)
    {
        CancellationTokenSource cts = new CancellationTokenSource();
        var deferral = taskInstance.GetDeferral();
        taskInstance.Canceled +=
            (sender, reason) =>
            {
                cts.Cancel();
            };
        try
        {
            await DownloadContactList(); // Do app migration/update steps.
        }
        catch (TaskCanceledException x)
        {
            // do nothing on cancelation.
        }
        deferral.Complete();
    }
}
```

## Preinstalls tasks for Classic Windows Apps

There are three deployments task types available to Classic Windows Apps, as shown in the table below. If you deploy your Classic Windows App on Windows 10, these tasks will work as expected.

| Task                   | Description                                                                                                                                                                |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PREINSTALL \_OEM\_TASK | A 1st or 2nd party preinstalled app can run at install time task without requiring the app to be launched by the end user.                                                 |
| UPDATE\_TASK           | After an app has been updated, including .appx to .uap, a servicing task can be run to carry out any migration related tasks, also without requiring any user interaction. |
| CONVERGENCE            | Windows 8.1 and Windows 8.1 Phone code convergence. Also, enable unified .appx manifest schema.                                                                            |
