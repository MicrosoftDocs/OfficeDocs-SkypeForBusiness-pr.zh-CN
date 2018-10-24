---
title: Set-CsBandwidthPolicyServiceConfiguration
TOCTitle: Set-CsBandwidthPolicyServiceConfiguration
ms:assetid: b39af1ca-465d-4598-96a3-e19283ddf731
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412863(v=OCS.15)
ms:contentKeyID: 49313991
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsBandwidthPolicyServiceConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing bandwidth policy service configuration. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsBandwidthPolicyServiceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsBandwidthPolicyServiceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-EnableLogging <$true | $false>] [-Force <SwitchParameter>] [-LogCleanUpInterval <TimeSpan>] [-MaxLogFileSizeMb <UInt32>] [-MaxTokenLifetime <TimeSpan>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example modifies the bandwidth policy service configuration for the site Redmond (-Identity site:Redmond). The configuration is modified to enable logging, change the maximum lifetime of a token to three hours, and the number of days before log cleanup to five days. This is all accomplished in this one command. To enable logging, the EnableLogging parameter is set to True ($true). Next the MaxTokenLifetime parameter receives a value of 3:00:00, which represents three hours. Finally, the LogCleanUpInterval parameter receives a value of 5.00:00:00, which signifies five days.

    Set-CsBandwidthPolicyServiceConfiguration -Identity site:Redmond -EnableLogging $true -MaxTokenLifetime 3:00:00 -LogCleanUpInterval 5.00:00:00

## Detailed Description

Call admission control (CAC) is a way of determining whether to allow real-time communications sessions, such as voice or video calls, to be established based on bandwidth constraints. Within the Lync Server implementation of CAC, regions, sites, and subnets are defined within a network along with the relationships and links between those entities in order to place bandwidth constraints between them. Bandwidth Policy service is the component that performs CAC functionality in the Lync Server deployment, enabling the decision as to whether sufficient bandwidth exists for a call to be established. This cmdlet modifies an existing bandwidth policy service configuration.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsBandwidthPolicyServiceConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsBandwidthPolicyServiceConfiguration"}

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
<td><p><em>EnableLogging</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Set this parameter to True to generate CAC failure and link status logs related to the bandwidth policy service.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>The unique identifier of the configuration you want to change. This identifier will consist of the scope (for the global configuration) or the scope and name (for a site-level configuration, such as site:Redmond).</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>BandwidthPolicyServiceConfiguration</p></td>
<td><p>A reference to a bandwidth policy service configuration object. This object must be of type BandwidthPolicyServiceConfiguration, which can be retrieved by calling the <strong>Get-CsBandwidthPolicyServiceConfiguration</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>LogCleanUpInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>The period of time after which CAC failure and link status logs will be removed.</p>
<p>This value must be within the range 1 day through 60 days. The value must be entered in the format dd.hh:mm:ss, where d is days, h is hours, m is minutes, and s is seconds. For example, 20 days would be 20.00:00:00.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxLogFileSizeMb</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The maximum size the log file is allowed to reach. The value for this parameter must be a positive number and specifies the file size in megabytes. For example, to allow the log file to reach a maximum size of 10 megabytes, enter the value 10.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxTokenLifetime</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>The maximum amount of time the token issued by the Bandwidth Policy Authentication service will exist.</p>
<p>This value must be in the range 1 hour through 24 hours. The value must be entered in the format dd.hh:mm:ss, where d is days, h is hours, m is minutes, and s is seconds. For example, the value for 12 hours would be 12:00:00.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.BandwidthPolicyServiceConfiguration.BandwidthPolicyServiceConfiguration object. Accepts pipelined input of bandwidth policy service configuration objects.

## Return Types

This cmdlet does not return a value. It modifies an object of type Microsoft.Rtc.Management.WritableConfig.Settings.BandwidthPolicyServiceConfiguration.BandwidthPolicyServiceConfiguration.

## 另请参阅

#### 其他资源

[New-CsBandwidthPolicyServiceConfiguration](new-csbandwidthpolicyserviceconfiguration.md)  
[Remove-CsBandwidthPolicyServiceConfiguration](remove-csbandwidthpolicyserviceconfiguration.md)  
[Get-CsBandwidthPolicyServiceConfiguration](get-csbandwidthpolicyserviceconfiguration.md)

