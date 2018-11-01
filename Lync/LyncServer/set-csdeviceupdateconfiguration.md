---
title: Set-CsDeviceUpdateConfiguration
TOCTitle: Set-CsDeviceUpdateConfiguration
ms:assetid: 4f200a03-984a-4c5b-a9c1-a866ba1851cd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398320(v=OCS.15)
ms:contentKeyID: 49312813
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsDeviceUpdateConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies a collection of 设备更新 Web 服务 configuration settings. These settings are used to manage the 设备更新 Web 服务, a Lync Server component that enables administrators to distribute firmware updates to telephones and other devices running Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsDeviceUpdateConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsDeviceUpdateConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-LogCleanUpInterval <TimeSpan>] [-LogCleanUpTimeOfDay <DateTime>] [-LogFlushInterval <TimeSpan>] [-MaxLogCacheLimit <UInt32>] [-MaxLogFileSize <UInt32>] [-ValidLogFileExtensions <PSListModifier>] [-ValidLogFileTypes <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 shows how the **Set-CsDeviceUpdateConfiguration** cmdlet can be used to modify the global configuration settings. In this case, two property values are modified: the MaxLogFileSize property is set to 2048000 bytes and the MaxLogCacheLimit property is set to 1024000 bytes.

    Set-CsDeviceUpdateConfiguration -Identity global -MaxLogFileSize 2048000 -MaxLogCacheLimit 1024000

## EXAMPLE 2

Example 2 modifies the LogFlushInterval property for the device update configuration settings with the Identity site:Redmond. To do this, the Identity parameter is used to specify the settings at the Redmond site and the LogFlushInterval parameter is used to indicate the property value that be changed. In this case, the LogFlushInterval is set to 2 minutes (00 hours: 02 minutes: 00 seconds).

    Set-CsDeviceUpdateConfiguration -Identity site:Redmond -LogFlushInterval 00:02:00

## EXAMPLE 3

In Example 3, all of the device configuration update settings in the organization are modified in order to set the LogCleanUpInterval to 14 days. To do this, the **Get-CsDeviceUpdateConfiguration** cmdlet is first used to retrieve a collection of all the device update configuration settings currently in use. This collection is then piped to the **Set-CsDeviceUpdateConfiguration** cmdlet, which uses the LogCleanUpInterval parameter to set the log clean up interval time for each item in the collection to 14 days (14 days . 00 hours : 00 minutes : 00 seconds).

    Get-CsDeviceUpdateConfiguration | Set-CsDeviceUpdateConfiguration -LogCleanUpInterval 14.00:00:00

## EXAMPLE 4

Example 4 demonstrates how you can modify a property value for all the device update configuration settings that have been configured at the site scope; in this case, the command sets the LogCleanUpInterval to 20 days (20 days . 00 hours : 00 minutes : 00 seconds). In order to do this, the **Get-CsDeviceUpdateConfiguration** cmdlet is used along with the Filter parameter; the filter value "site:\*" limits the returned data to settings that have an Identity that begins with the string value "site:". This filtered collection is then piped to the **Set-CsDeviceUpdateConfiguration** cmdlet, which changes the value of the log cleanup interval for each item in the collection.

    Get-CsDeviceUpdateConfiguration -Filter "site:*" | Set-CsDeviceUpdateConfiguration -LogCleanUpInterval 20.00:00:00

## EXAMPLE 5

Example 5 removes CELog from the list of valid log file types used by the device update configuration settings. In this command, the **Get-CsDeviceUpdateConfiguration** cmdlet is first used to retrieve a collection of all the device update configuration settings currently in use in the organization. That collection is then piped to the **Set-CsDeviceUpdateConfiguration** cmdlet, which uses the ValidLogFileTypes parameter in order to remove CELog from the list of valid log file types. The parameter value passed to ValidLogFileTypes, @{Remove="CELog"}, instructs the **Set-CsDeviceUpdateConfiguration** cmdlet to remove CELog from the set of valid file types. To remove multiple files types in a single command, simply include the additional types as part of a comma-separated list. For example:

@{Remove="CELog","Watson"}

    Get-CsDeviceUpdateConfiguration | Set-CsDeviceUpdateConfiguration -ValidLogFileTypes @{Remove="CELog"}

## Detailed Description

The 设备更新 Web 服务 provides a way for administrators to distribute firmware updates to devices that run Lync Phone Edition. Periodically, administrators upload a set of device update rules to Lync Server. After those rules have been tested and approved, they can then be applied to the appropriate devices as those devices connect to the system. Devices check for updates when they are first powered on, then check again when a user logs on. After that, devices will check for updates every 24 hours.

Device update configuration settings can be applied at either the global or the site scope. The **Set-CsDeviceUpdateConfiguration** cmdlet enables you to make changes to a collection of settings. For example, you can use this cmdlet to change the length of time a log file is kept before it is automatically deleted by the system).

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsDeviceUpdateConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsDeviceUpdateConfiguration"}

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
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the device update configuration settings to be modified. To refer to the global settings, use this syntax: -Identity global. To refer to site settings, use syntax similar to this: -Identity &quot;site:Redmond&quot;. Note that you cannot use wildcards when specifying an Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>DeviceUpdateSettings object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
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
<p>The value passed to the LogCleanupTimeOfDay parameter should be in the 24-hour time format hh:mm, where hh represents the hours and mm represents the minutes. In this format, midnight is represented as 00:00; 8:30 A.M. is represented as 08:30; and 11:52 P.M. is represented as 23:52.</p></td>
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
<td><p>Indicates the maximum amount of information (in bytes) that can held in the log file cache before that cache must be cleared and the data written to a log file. By default, log files are &quot;flushed&quot; every 5 minutes. (For details, see the description of the parameter LogFlushInterval.) However, if the cache reaches its maximum size the information in it will automatically be written to a log file (and the cache cleared), even if the log flush interval has not yet expired.</p>
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
<td><p>Indicates the valid log file extensions that can be used with the Device Update Web service. This list can be modified; however, there is no reason to modify the list unless you have a Lync Phone Edition compatible device that creates log files that use a different file extension.</p>
<p>Default: .dmp, .clg, .clg2, .bak, .kdmp, .dat, .bin, .cat, .xml, .txt, .hex</p></td>
</tr>
<tr class="odd">
<td><p><em>ValidLogFileTypes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Indicates the log file types retained by the device update system. The default file types include the following:</p>
<p>Watson. Log files automatically generated by a device in the event of a system crash.</p>
<p>CELog. Lync Phone logs that contain the results of functional tests and also a record of critical system events.</p>
<p>Additional file types can be added if you have a Lync Phone Edition-compatible device that creates a different kind of log file. You can also remove files. For example, if you do not want to store CELog files then you can remove the CELog file type.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.DeviceUpdateConfiguration object. The **Set-CsDeviceUpdateConfiguration** cmdlet accepts pipelined instances of the device update configuration object.

## Return Types

The **Set-CsDeviceUpdateConfiguration** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.DeviceUpdateConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsDeviceUpdateConfiguration](get-csdeviceupdateconfiguration.md)  
[New-CsDeviceUpdateConfiguration](new-csdeviceupdateconfiguration.md)  
[Remove-CsDeviceUpdateConfiguration](remove-csdeviceupdateconfiguration.md)

