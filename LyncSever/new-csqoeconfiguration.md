---
title: New-CsQoEConfiguration
TOCTitle: New-CsQoEConfiguration
ms:assetid: 4fc607d5-1a85-4de5-9d18-39d0425c82dc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398325(v=OCS.15)
ms:contentKeyID: 49312826
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsQoEConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of QoE (Quality of Experience) settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsQoEConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-EnableExternalConsumer <$true | $false>] [-EnablePurging <$true | $false>] [-EnableQoE <$true | $false>] [-ExternalConsumerIssuedCertId <IssuedCertId>] [-ExternalConsumerName <String>] [-ExternalConsumerURL <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-KeepQoEDataForDays <UInt32>] [-PurgeHourOfDay <UInt32>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command in Example 1 uses the **New-CsQoEConfiguration** cmdlet to create a new set of Quality of Experience settings with the Identity site:Redmond. In addition to the Identity site:Redmond, the new settings also have the EnableQoE property set to False. Because site settings take precedence over global settings, this means that QoE will be disabled for the Redmond site, regardless of whether or not QoE has been enabled at the global scope.

    New-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False

## EXAMPLE 2

This command creates new QoE settings that apply to the Dublin site. In this example we’ve set the KeepQoEDataForDays parameter to 30, so QoE data will be purged from the database after 30 days rather than the default 60 days. In addition, we’ve set the PurgeHourOfDay parameter to 4, meaning any data older than the 30 days we just specified will be purged at 4:00 AM.

Note: If you have enabled QoE and call detail recording (CDR), for performance reasons it’s a good idea to make sure the PurgeHourOfDay setting is different for QoE than for CDR.

    New-CsQoEConfiguration -Identity site:Dublin -KeepQoEDataForDays 30 -PurgeHourOfDay 4

## Detailed Description

QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording. Use this cmdlet to create settings that configure QoE at the site level. (Settings at the global level exist by default and cannot be removed.)

QoE is part of the 监控服务器 role; therefore 监控服务器 must be deployed on your Lync Server installation before QoE recording takes effect or any QoE data can be collected.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsQoEConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsQoEConfiguration"}

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
<td><p>The site to which the new settings apply. This must be entered in the format site:&lt;site name&gt;, where &lt;site name&gt; is the name of the site in your Lync Server deployment.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableExternalConsumer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Specifies whether an external consumer is able to receive QoE reports.</p>
<p>Default: False</p></td>
</tr>
<tr class="even">
<td><p><em>EnablePurging</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Specifies whether records will be purged after the duration defined in the KeepQoEDataForDays property has elapsed.</p>
<p>Default: True</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableQoE</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Specifies whether QoE records will be collected and saved to the monitoring database.</p>
<p>Note that even if EnableQoE is set to True, QoE data will not be collected unless a 监控服务器 has been deployed and associated with a Registrar pool.</p>
<p>Default: True</p></td>
</tr>
<tr class="even">
<td><p><em>ExternalConsumerIssuedCertId</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.BaseTypes.IssuedCertId</p></td>
<td><p>The certificate ID of the certificate that allows access to the external consumer web service.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExternalConsumerName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The friendly name of the external consumer of the QoE report.</p></td>
</tr>
<tr class="even">
<td><p><em>ExternalConsumerURL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The URL of the external consumer to which the QoE reports will be posted.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>KeepQoEDataForDays</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The number of days QoE data will be stored before being purged from the database. This value is ignored if EnablePurging is set to False.</p>
<p>Must be a value from 1 through 2562.</p>
<p>Default: 60</p></td>
</tr>
<tr class="even">
<td><p><em>PurgeHourOfDay</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The hour of day that QoE records that have exceeded the number of days specified in the KeepQoEDataForDays property will be purged.</p>
<p>Must be a value 0 through 23, representing the hour of the day. For example, 0 would be midnight, 13 would be 1:00 PM. Default: 1</p></td>
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

Creates an object of type Microsoft.Rtc.Management.WritableConfig.Settings.QoE.QoESettings.

## 另请参阅

#### 其他资源

[Remove-CsQoEConfiguration](remove-csqoeconfiguration.md)  
[Set-CsQoEConfiguration](set-csqoeconfiguration.md)  
[Get-CsQoEConfiguration](get-csqoeconfiguration.md)

