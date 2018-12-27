---
title: Assessment Platform Command-Line Syntax
description: Command-line syntax for AXE.com, which enables running and analyzing jobs with the Assessment Platform.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 34286b79-1867-4d0d-8b65-6a0c6a7e5df8
ms.mktglfcycl: plan
ms.sitesec: msdn

ms.date: 10/27/2017
ms.topic: article


---

# Assessment Platform Command-Line Syntax


The Assessment Platform is available for use from the command line by using AXE.exe, a command-line tool that you can use to automate jobs from a script and minimize resource usage. In addition, command-line options provide access to parameters that are not available through the [Windows Assessment Console](windows-assessment-console.md).

AXE.exe has limitations: You cannot use it to run a preconfigured job or one of the single assessments provided by the Windows Assessment Toolkit. You also cannot create or modify a job by using AXE.exe; for creating or modifying a job, you must use the Windows Assessment Console.

AXE.exe is installed with the [Windows Assessment Toolkit](index.md), and by default it is installed to the following folder:

<p style="margin: 1em 0 1em 1.5em;">%ProgramFiles(x86)%\Windows Kits\10\Assessment and Deployment Kit\Windows Assessment Toolkit&lt;em&gt;architecture</em>&lt;/p&gt;

<p>where <em>architecture</em> is one of the following: <strong>amd64</strong>, <strong>arm</strong>, <strong>arm64</strong>, <strong>x86</strong>.</p>



## Command-Line Options

AXE.exe uses the following syntax:

<p style="margin: 1em 0 0 1.5em;"><strong>axe</strong>&nbsp;<em>job_file</em> <strong>/Timeout</strong>&nbsp;<em>seconds</em>] [<strong>/NoPublish</strong>] [<strong>/PublishPath</strong>&nbsp;<em>folder_path</em>] [<strong>/RemoveRestart</strong>] [<strong>/DisplayLog</strong>&nbsp;<em>ETL_file</em>] [<strong>/NoWarnings</strong>] [<strong>/JobParameter</strong> <em>parameter</em><strong>=</strong><em>value</em>] [<strong>/Pause</strong>]</p>

<p style="margin: 1em 0 0 1.5em;"><strong>axe</strong>&nbsp;<strong>/Analyze</strong> <em>results_file</em> [<strong>/Job</strong> <em>job_file</em>] [<strong>/Assessment</strong> <em>assessment_file</em>]</p>

<p>These options are described in the following table. The names of these options are not case-sensitive.</p>
<br/>
<table>
<thead>
<tr class="header">
<th bgcolor="EEEEEE"><p style="text-align: center; margin: 0 0 0 0">Option</p></th>
<th bgcolor="EEEEEE"><p style="text-align: center; margin: 0 0 0 0">Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Help</strong> or <strong>/?</strong></p></td>
<td><p>Displays information about available AXE.exe command-line options.</p></td>
</tr>
<tr class="even">
<td><p><em>job_file</em></p></td>
<td><p>Specifies the job (.jobx) file that you want to run, and <em>job_file</em> can specify a relative path. If the job file is in the directory from which you&#39;re running AXE.exe, no path is required.</p>
<p>By default, when you create a job in the Windows Assessment Console, it&#39;s saved in to %USERPROFILE%\Documents\Windows Assessment Console\Jobs\.</p>
<p style="margin: 1em 1.5em 0 1.5em;"><strong>Note</strong>&nbsp;&nbsp;&nbsp;This option is required if no other parameter that performs an action is specified.</p>
<p>Example:</p>
<code>axe&nbsp;C:\Assessments\MyJobs\Job1.jobx</code></td>
</tr>
<tr class="odd">
<td><p><strong>/Job</strong> <em>job_file</em></p></td>
<td><p>Specifies the path and file name of the job file, <em>job_file</em>, to use in locating the assessments to reanalyze within the results file.</p>
</td>
</tr>
<tr class="even">
<td><p><strong>/Analyze</strong> <em>results_file</em></p></td>
<td><p>Reanalyzes the results from a job (.jobx) file specified by <em>results_file</em>. This option requires a job from a package or assessment manifest directly to locate the assessments to reanalyze.</p>
<!--joshbax, 2017-10-26: I haven't figured out a functional example for /Analyze that definitely seems to work.
<p>Example:</p>
<code>axe&nbsp;C:\\Assessments\\MyJobs\\Job1.jobx /Analyze C:\\Assessments\\MyResults\\JobResults_COMPUTERNAME_2017-1026_0929-27.803\\JobResults_COMPUTERNAME_2017-1026_0929-27.803.xml</code>-->
</td>
</tr>
<tr class="odd">
<td><p><strong>/Assessment</strong> <em>assessment_file</em></p></td>
<td><p>Specifies the path and file name of an assessment manifest, <em>assessment_file</em>, to reanalyze in the results file specified.</p>
<!--joshbax, 2017-10-26: I haven't figured out a functional example for /Assessment that definitely seems to work.
<p>Example:</p>
<code>axe&nbsp;C:\Assessments\MyJobs\Job1.jobx /Analyze %UserProfile%\\AppData\\Local\\Microsoft\\Axe\\Results\\JobResults_COMPUTERNAME_2017-1026_0929-27.803\\JobResults_COMPUTERNAME_2017-1026_0929-27.803.xml /Assessment </code>-->
</td>
</tr>
<tr class="even">
<td><p><strong>/Timeout</strong>&nbsp;<em>seconds</em></p></td>
<td><p>Specifies the amount of time in <em>seconds</em> that the job will wait for another job to finish before it exits with an error. When <em>seconds</em> is zero, the default, the job will exit immediately without running if another job is already running.</p>
<p>Example:</p>
<code>axe&nbsp;C:\Assessments\myJobs\Job1.jobx /Timeout 30</code></td>
</tr>
<tr class="odd">
<td><p><strong>/NoPublish</strong></p></td>
<td><p>Specifies to <em>not</em> publish the results file to the location that&#39;s specified in the job file. When you use this option, the results are saved to the default location, %LOCALAPPDATA%\Microsoft\Axe\Results\.</p>
<p>Example:</p>
<code>axe&nbsp;C:\Assessments\myJobs\Job1.jobx /NoPublish</code></td>
</tr>
<tr class="even">
<td><p><strong>/PublishToSource</strong></p></td>
<td><p>Specifies that AXE.exe update the original results folder when running <strong>/Analyze</strong>. Using <strong>/PublishToSource</strong> is optional, and it is ignored when running a job.</p>
<p><strong>/PublishToSource</strong> may be combined with the publish path, but the publish path will only be used if AXE.exe cannot publish to the original results folder.</p>
<!--sapaetsc, 2017-10-27: The following example is non-functional, because no
file is specified for /Analyze.
<p>Example:</p>
<code>axe&nbsp;C:\\Assessments\\myJobs\\Job1.jobx  /Analyze /PublishToSource</code></td>-->
</tr>
<tr class="odd">
<td><p><strong>/PublishPath</strong>&nbsp;<em>folder_path</em></p></td>
<td><p>Specifies a location to publish the results file to. The path specified by <em>folder_path</em> overrides the publication path, <strong>ResultsPublishPath</strong>, that is specified in the job file. This option is ignored if it&#39;s combined with <strong>/NoPublish</strong>.</p>
<p>Example:</p>
<code>axe&nbsp;C:\Assessments\myJobs\Job1.jobx /PublishPath C:\Assessments\myResults</code></td>
</tr>
<tr class="even">
<td><p><strong>/DisplayLog</strong>&nbsp;<em>ETL_file</em></p></td>
<td><p>Displays the content of an Event Trace Log (ETL) file specified by <em>ETL_file</em>, which can contain wildcard characters in the path and file name. AXE.exe writes an ETL file when running a job, and it displays the path in the console window.</p>
<p>The default location of the log file is %LOCALAPPDATA%\Microsoft\Axe\Logs\<em>GUID</em>\, where <em>GUID</em> is a GUID that is generated randomly for each new job. The job results file in the <strong>SessionLogFiles</strong> node also contains the full location. This node specifies all of the log files.</p>
<p style="margin: 1em 1.5em 0 1.5em;"><strong>Note</strong>&nbsp;&nbsp;&nbsp;All of the ETL files are automatically converted into a single AxeLog.txt file that is saved in the results directory. You can open this file by using Notepad.</p>
<p>Example:</p>
<code>axe&nbsp;/DisplayLog %LOCALAPPDATA%\Microsoft\Axe\Logs\E5A6CB43-C1CE-4FC1-8170-13B002E250B36\AxeLog-000.etl</code></td>
</tr>
<tr class="odd">
<td><p><strong>/RemoveRestart</strong></p></td>
<td><p>Specifies that any existing, pending job-restart task should be removed.</p>
<p style="margin: 1em 1.5em 0 1.5em;"><strong>Note</strong>&nbsp;&nbsp;&nbsp;The <strong>/JobFile</strong> option isn&#39;t needed when you use this option.</p>
<p>When you run a job, the assessment creates a task to restart the job if there&#39;s a system failure, like a loss of power. When you use this option, the task is removed from the Task Scheduler. If no job-restart task is pending, the assessment will return an error to inform you that the task doesn&#39;t exist.</p>
<p>Example:</p>
<code>axe&nbsp;/RemoveRestart</code></td>
</tr>
<tr class="even">
<td><p><strong>/NoWarnings</strong></p></td>
<td><p>Suppresses warning messages. This is an optional parameter.</p>
<p>Example:</p>
<code>axe&nbsp;C:\Assessments\myJobs\Job1.jobx /NoWarnings</code></td>
</tr>
<tr class="odd">
<td><p><strong>/Pause</strong></p></td>
<td><p>Pauses AXE.exe after the job finishes. You can then see any errors or other information in the console before AXE.exe exits and the console closes. Exiting continues when you press a key.</p>
<p>Example:</p>
<code>axe&nbsp;C:\Assessments\myJobs\Job1.jobx /Pause</code></td>
</tr>
<tr class="even">
<td><p><strong>/JobParameter</strong> <em>parameter</em><strong>=</strong><em>value</em></p></td>
<td><p>Specifies a <em>value</em> to override a job <em>parameter</em> that may exist in the job manifest. You can use <strong>/JobParameter</strong> up to 100 times to specify multiple job parameters. If duplicate parameter names appear, the assessment uses the last value supplied for that name. Using <strong>/JobParameter</strong> is optional.</p>
<p>The <strong>/PublishPath</strong> option takes precedence over setting the <strong>ResultsPublishPath</strong> job parameter with this option.</p>
<p>Example:</p>
<code>axe&nbsp;C:\Assessments\myJobs\Job1.jobx /JobParameter iterations=1</code></td>
</tr>
</tbody>
</table>



 
## Related topics

[Windows Assessment Console Overview](windows-assessment-console-overview.md)

 

 
