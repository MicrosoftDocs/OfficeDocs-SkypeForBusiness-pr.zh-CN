---
title: New-CsDeviceUpdateConfiguration
TOCTitle: New-CsDeviceUpdateConfiguration
ms:assetid: 2a06450d-291e-40f9-a780-45e2c4b28494
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425761(v=OCS.15)
ms:contentKeyID: 49312323
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsDeviceUpdateConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new instance of device update configuration settings. These settings are used to manage the 设备更新 Web 服务, a Lync Server component that enables administrators to distribute firmware updates to telephones and other devices running Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsDeviceUpdateConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-LogCleanUpInterval <TimeSpan>] [-LogCleanUpTimeOfDay <DateTime>] [-LogFlushInterval <TimeSpan>] [-MaxLogCacheLimit <UInt32>] [-MaxLogFileSize <UInt32>] [-ValidLogFileExtensions <PSListModifier>] [-ValidLogFileTypes <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new set of device update configuration settings with the Identity site:Redmond. Because no other parameters are included in the command, this new collection of configuration settings will use the default values for each property.

    New-CsDeviceUpdateConfiguration -Identity site:Redmond

## EXAMPLE 2

Example 2 also creates a new set of device update configuration settings with the Identity site:Redmond. In this case, two additional parameters are used in order to customize the new settings: MaxLogFileSize is used to set the maximum log file size to 2048000 bytes, while LogCleanUpInterval is used to set the log cleanup interval time to 7 days (7 days . 00 hours : 00 minutes : 00 seconds).

    New-CsDeviceUpdateConfiguration -Identity site:Redmond -MaxLogFileSize 204800 -LogCleanUpInterval 7.00:00:00

## Detailed Description

The 设备更新 Web 服务 provides a way for administrators to distribute firmware updates to devices that run Lync Server. Periodically, administrators upload a set of device update rules to Lync Server. After those rules have been tested and approved, they can then be applied to the appropriate devices as those devices connect to the system. Devices check for updates when they are first powered on, then check again when a user logs on. After that, devices check for updates every 24 hours.

Device update configuration settings, which are used to manage the 设备更新 Web 服务, can be assigned to the global level or to the site scope. To create a new collection of settings for a site, use the **New-CsDeviceUpdateConfiguration** cmdlet. Note that you can only create new settings at the site scope; your command will fail if you try to create a new collection of settings at the global scope. In addition, your command will fail if you try to create a new collection of settings for, say, the Redmond site, and that site already hosts a collection of device update configuration settings. That’s because you can only have one collection of device update configuration settings per site.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsDeviceUpdateConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsDeviceUpdateConfiguration"}

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the Identity of the new device update configuration settings. Because new settings can only be created at the site scope, the Identity will look something like this: -Identity &quot;site:Redmond&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>LogCleanUpInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Specifies the amount of time a device update log file is kept before it is deleted by the system.</p>
<p>The value must be entered in the format dd.hh:mm:ss where dd is days, hh is hours, mm is minutes, and ss is seconds. To enter only days, you must follow the value with a period (.).</p>
<p>Minimum Value: 1.00:00:00 (1 Day)</p>
<p>Maximum Value: 365.00:00:00 (1 Year)</p>
<p>Default: 10.00:00:00 (10 Days)</p></td>
</tr>
<tr class="even">
<td><p><em>LogCleanUpTimeOfDay</em></p></td>
<td><p>Optional</p></td>
<td><p>System.DateTime</p></td>
<td><p>Indicates the time of day when the system checks to see if there are any expired log files that should be deleted. (Expired log files are any files older than the value specified in by the LogCleanupInterval property.)</p>
<p>The value passed to the LogCleanupTimeOfDay parameter must be in the 24-hour time format hh:mm, where hh represents the hours and mm represents the minutes. In this format, midnight is represented as 00:00; 8:30 A.M. is represented as 08:30; and 11:52 P.M. is represented as 23:52. The default value is null.</p></td>
</tr>
<tr class="odd">
<td><p><em>LogFlushInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Indicates how often information stored in the log file cache is written to the actual log file. By default, device update information is not immediately written to the log file; instead, that information is cached in memory until: 1) the log flush time interval has expired; or, 2) the cache has reached its maximum size. If this value is set to 10 minutes (00:10:00), then information in the cache will be written to the log file every 10 minutes. After the data has been logged the cache will be cleared.</p>
<p>The value must be entered in the format hh:mm:ss where hh is hours, mm is minutes, and ss is seconds.</p>
<p>Minimum Value: 00:01:00 (1 minute)</p>
<p>Maximum Value: 1:00:00 (1 hour)</p>
<p>Default: 00:05:00</p></td>
</tr>
<tr class="even">
<td><p><em>MaxLogCacheLimit</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data written to a log file. By default, log files are &quot;flushed&quot; every X number of minutes. (For details, see the description of the parameter LogFlushInterval.) However, if the cache reaches its maximum size, the information in it will automatically be written to a log file (and the cache cleared) even if the log flush interval has not yet expired.</p>
<p>Default: 512000</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxLogFileSize</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the maximum size, in bytes, for an individual log file. When a file reaches the maximum size, the next batch of data is automatically written to a new log file. The old log file will be retained until the log cleanup interval has expired.</p>
<p>Default: 1024000</p></td>
</tr>
<tr class="even">
<td><p><em>ValidLogFileExtensions</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Indicates the valid log file extensions that can be used with the 设备更新 Web 服务. This list can be modified; however, there is no reason to modify the list unless you have a device running Lync Server that creates log files that use a different file extension.</p>
<p>Default: .dmp, .clg, .clg2, .bak, .kdmp, .dat, .bin, .cat, .xml, .txt, .hex</p></td>
</tr>
<tr class="odd">
<td><p><em>ValidLogFileTypes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Indicates the log file types retained by the device update system. The default file types include the following:</p>
<p>Watson. Log files automatically generated by a device if the system stops responding.</p>
<p>CELog. Logs for phones running Lync that contain the results of functional tests and a record of critical system events.</p>
<p>Additional file types can be added if you have a device running Lync Phone Edition that creates a different kind of log file. You can also remove files. For example, if you do not want to store CELog files then you can remove the CELog file type.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsDeviceUpdateConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **New-CsDeviceUpdateConfiguration** cmdlet creates instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.DeviceUpdateConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsDeviceUpdateConfiguration](get-csdeviceupdateconfiguration.md)  
[Remove-CsDeviceUpdateConfiguration](remove-csdeviceupdateconfiguration.md)  
[Set-CsDeviceUpdateConfiguration](set-csdeviceupdateconfiguration.md)

