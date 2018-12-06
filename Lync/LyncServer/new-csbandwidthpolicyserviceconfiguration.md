---
title: New-CsBandwidthPolicyServiceConfiguration
TOCTitle: New-CsBandwidthPolicyServiceConfiguration
ms:assetid: 0cb07eda-ffbe-48e2-b6bc-995737e5ba32
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398175(v=OCS.15)
ms:contentKeyID: 49311986
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsBandwidthPolicyServiceConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new bandwidth policy service configuration. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsBandwidthPolicyServiceConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-EnableLogging <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-LogCleanUpInterval <TimeSpan>] [-MaxLogFileSizeMb <UInt32>] [-MaxTokenLifetime <TimeSpan>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example creates a new bandwidth policy service configuration at the site Redmond (-Identity site:Redmond). No other parameters are specified, so the defaults are used for all configuration values.

    New-CsBandwidthPolicyServiceConfiguration -Identity site:Redmond

## EXAMPLE 2

In this example we again create a new bandwidth policy service configuration, this time for the Dublin site (-Identity site:Dublin). For this site, rather than accepting the default values, we want to enable logging and set the number of days that pass before logs are cleaned up to 30 days. We do this by passing a value of True ($True) to the EnableLogging parameter, and then passing a value of 30.00:00:00 to the parameter LogCleanupInterval. The LogCleanupInterval value is a TimeSpan object, which is in the format dd.hh:mm:ss, where d is days, h is hours, m is minutes, and s is seconds.

    New-CsBandwidthPolicyServiceConfiguration -Identity site:Dublin -EnableLogging $True -LogCleanupInterval 30.00:00:00

## Detailed Description

Call admission control (CAC) is a way of determining whether to allow real-time communications sessions, such as voice or video calls, to be established based on bandwidth constraints. Within the Lync Server implementation of CAC, regions, sites, and subnets are defined within a network along with the relationships and links between those entities in order to place bandwidth constraints between them. Bandwidth Policy service is the component that performs CAC functionality in the Lync Server deployment, enabling the decision as to whether sufficient bandwidth exists for a call to be established. This cmdlet configures a new bandwidth policy service at the site level.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsBandwidthPolicyServiceConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsBandwidthPolicyServiceConfiguration"}

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
<td><p>A unique identifier that contains the scope and name of the configuration. This configuration can be created only at the site scope, so the Identity will be in the following format: site:&lt;site name&gt;, where &lt;site name&gt; is the name of the site to which the configuration applies.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableLogging</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Set this parameter to True to generate CAC failure and link status logs related to the bandwidth policy service.</p>
<p>Default: False</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>LogCleanUpInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>The period of time after which CAC failure and link status logs will be removed.</p>
<p>This value must be within the range 1 day through 60 days. The value must be entered in the format dd.hh:mm:ss, where d is days, h is hours, m is minutes, and s is seconds.</p>
<p>Default: 10 days (10.00:00:00)</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxLogFileSizeMb</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The maximum size the log file is allowed to reach. The value for this parameter must be a positive number; it specifies the file size in megabytes.</p>
<p>Default: 3 (MB)</p></td>
</tr>
<tr class="even">
<td><p><em>MaxTokenLifetime</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>The maximum amount of time the token issued by the Bandwidth Policy Authentication service will exist.</p>
<p>This value must be in the range 1 hour through 24 hours. The value must be entered in the format dd.hh:mm:ss, where d is days, h is hours, m is minutes, and s is seconds.</p>
<p>Default: 8 hours (08:00:00)</p></td>
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

None.

## Return Types

Creates an object of type Microsoft.Rtc.Management.WritableConfig.Settings.BandwidthPolicyServiceConfiguration.BandwidthPolicyServiceConfiguration.

## 另请参阅

#### 其他资源

[Remove-CsBandwidthPolicyServiceConfiguration](remove-csbandwidthpolicyserviceconfiguration.md)  
[Set-CsBandwidthPolicyServiceConfiguration](set-csbandwidthpolicyserviceconfiguration.md)  
[Get-CsBandwidthPolicyServiceConfiguration](get-csbandwidthpolicyserviceconfiguration.md)

