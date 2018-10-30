---
title: Set-CsClsConfiguration
TOCTitle: Set-CsClsConfiguration
ms:assetid: 6cebd908-e829-4dee-82fd-1164bc8999ee
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619182(v=OCS.15)
ms:contentKeyID: 49313175
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsClsConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing collection of centralized logging configuration settings. Centralized logging provides a way for administrators to simultaneously enable or disable tracing on multiple computers. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsClsConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsClsConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-CacheFileLocalFolders <String>] [-CacheFileLocalMaxDiskUsage <UInt32>] [-CacheFileLocalRetentionPeriod <UInt32>] [-CacheFileNetworkFolder <String>] [-ComponentThrottleLimit <UInt32>] [-ComponentThrottleSample <UInt32>] [-Confirm [<SwitchParameter>]] [-EtlFileFolder <String>] [-EtlFileRolloverMinutes <UInt32>] [-EtlFileRolloverSizeMB <UInt32>] [-Force <SwitchParameter>] [-MinimumClsAgentServiceVersion <UInt32>] [-Regions <PSListModifier>] [-Scenarios <PSListModifier>] [-SearchTerms <PSListModifier>] [-SecurityGroups <PSListModifier>] [-TmfFileSearchPath <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

In Example 1, the global collection of centralized logging configuration settings is modified to set the maximum size of an ETL file to 40 megabytes.

    Set-CsClsConfiguration -Identity "global" -EtlRolloverFileSizeMB 40

## Example 2

The command shown in Example 2 modifies the maximum ETL file size for all the centralized logging configuration settings in use in the organization. To do this, the command first calls the **Get-CsClsConfiguration** cmdlet to return a collection of all the centralized logging settings. That collection is then piped to the **Set-CsClsConfiguration** cmdlet, which changes the value of the EtlRolloverFileSizeMB property for each item in the collection to 40 megabytes.

    Get-CsClsConfiguration | Set-CsClsConfiguration -EtlRolloverFileSizeMB 40

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

Centralized logging is built around a series of predefined scenarios that offer a more finely-targeted approach to logging than offered in previous versions of Lync Server. These scenarios predetermine the server components and logging for you; as a result, an administrator enabling the RGS scenario can be confident that he or she will only log information relevant to the Response Group service and not to, say, the audio conferencing provider service.

It is also possible to define custom scenarios by using the [New-CsClsScenario](new-csclsscenario.md) cmdlet.

Centralized logging is managed by using collections of centralized logging service configuration settings. When you install Lync Server 2013, you install a global set of these configuration settings; in addition, administrators can add custom settings collections at the site scope. Administrators can use the **Set-CsClsConfiguration** cmdlet to modify any of these settings.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsClsConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsClsConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>CacheFileLocalFolders</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>One or more full paths to the local folders where the cache files will be stored. The default value is %TEMP%\Tracing. If more than one path is specified, then separate them with semi-colons.</p></td>
</tr>
<tr class="even">
<td><p><em>CacheFileLocalMaxDiskUsage</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum amount of disk space (percentage) that can be used for the cache files. The default value is 80.</p></td>
</tr>
<tr class="odd">
<td><p><em>CacheFileLocalRetentionPeriod</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum number of days that cache files are retained locally. The default value is 14.</p></td>
</tr>
<tr class="even">
<td><p><em>CacheFileNetworkFolder</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Full UNC path to the network cache folder. There is no default value.</p></td>
</tr>
<tr class="odd">
<td><p><em>ComponentThrottleLimit</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum rate at which a component is allowed to generate trace records before its tracing is throttled. The default value is 5000 trace calls per second.</p>
<p>The default value is 5000.</p></td>
</tr>
<tr class="even">
<td><p><em>ComponentThrottleSample</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum number of times the ComponentThrottleLimit can be exceeded within a one minute interval. The default value is 3.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>EtlFileFolder</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Full path to the folder where the event log trace files will be stored. The default value is %TEMP%\Tracing. Note that %TEMP% is evaluated in the contents of the CLS Service so it actual expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</p></td>
</tr>
<tr class="odd">
<td><p><em>EtlFileRolloverMinutes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum amount of time (in minutes) that can elapse before a new event log trace file is created. (This new file will be created even if the existing trace file has not reached the specified rollover size.) The default value is 60.</p></td>
</tr>
<tr class="even">
<td><p><em>EtlFileRolloverSizeMB</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum size (in megabytes) that at event trace log file can reach before a new file is created. The default value is 20.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the centralized logging configuration settings to be modified. To refer to the global settings, use this syntax:</p>
<p>-Identity global</p>
<p>To refer to site settings, use syntax similar to this:</p>
<p>-Identity site:Redmond</p>
<p>You cannot use wildcards when specifying an Identity.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object rather than set individual parameter values.</p></td>
</tr>
<tr class="even">
<td><p><em>MinimumClsAgentServiceVersion</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Specifies the minimum version of the centralized logging service agent to be used when logging data; any computers with an agent version lower than the minimum value will be excluded from the logging operations. The default value is 6, representing Lync Server 2013. This parameter is intended for use with Skype for Business Online.</p></td>
</tr>
<tr class="odd">
<td><p><em>Regions</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Collection of regions defined for the centralized logging configuration settings. Regions are defined using the New-CsClsRegion cmdlet.</p>
<p>This parameter is intended for use with Skype for Business Online.</p></td>
</tr>
<tr class="even">
<td><p><em>Scenarios</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Collection of components/situations that can be traced using centralized logging. Scenarios are managed using the <strong>CsClsScenario</strong> cmdlets.</p></td>
</tr>
<tr class="odd">
<td><p><em>SearchTerms</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Collection of terms that help determine the personally identifiable information available to technical support personnel who search the centralized logging files. Search terms are managed using the <strong>CsClsSearchTerm</strong> cmdlets.</p></td>
</tr>
<tr class="even">
<td><p><em>SecurityGroups</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Security groups who are allowed to access the log files.</p>
<p>This parameter is intended for use with Skype for Business Online.</p></td>
</tr>
<tr class="odd">
<td><p><em>TmfFileSearchPath</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Search path for TMF (trace message format) files. TMF files convert binary trace messages to a human-readable format.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Set-CsClsConfiguration** cmdlet accepts pipelined instances of the icrosoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.CentralizedLoggingConfiguration object.

## Return Types

None. Instead, the **Set-CsClsConfiguration** cmdlet modifies existing instances of the icrosoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.CentralizedLoggingConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsClsConfiguration](get-csclsconfiguration.md)  
[New-CsClsConfiguration](new-csclsconfiguration.md)  
[Remove-CsClsConfiguration](remove-csclsconfiguration.md)

