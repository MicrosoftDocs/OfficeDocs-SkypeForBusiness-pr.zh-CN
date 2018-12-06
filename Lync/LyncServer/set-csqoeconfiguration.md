---
title: Set-CsQoEConfiguration
TOCTitle: Set-CsQoEConfiguration
ms:assetid: 199f0127-7444-4f88-993a-8e6a33fdcb61
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398245(v=OCS.15)
ms:contentKeyID: 49312148
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsQoEConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing collection of QoE (Quality of Experience) settings. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsQoEConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsQoEConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-EnableExternalConsumer <$true | $false>] [-EnablePurging <$true | $false>] [-EnableQoE <$true | $false>] [-ExternalConsumerIssuedCertId <IssuedCertId>] [-ExternalConsumerName <String>] [-ExternalConsumerURL <String>] [-Force <SwitchParameter>] [-KeepQoEDataForDays <UInt32>] [-PurgeHourOfDay <UInt32>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command in Example 1 uses the **Set-CsQoEConfiguration** cmdlet to modify the Quality of Experience settings for the Redmond site (-Identity site:Redmond). The new settings turn off QoE by setting the EnableQoE parameter to False.

    Set-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False

## EXAMPLE 2

This command modifies QoE settings that apply to the Dublin site. In this example we’ve set the KeepQoEDataForDays parameter to 45, so QoE data will be purged from the database after 45 days. In addition, we’ve set the PurgeHourOfDay parameter to 4, meaning any data older than the 45 days we just specified will be purged at 4:00 AM.

Note: If you have enabled QoE and call detail recording (CDR), for performance reasons it’s a good idea to make sure the PurgeHourOfDay setting is different for QoE than for CDR.

    Set-CsQoEConfiguration -Identity site:Dublin -KeepQoEDataForDays 45 -PurgeHourOfDay 4

## Detailed Description

QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording. Use this cmdlet to modify settings that configure QoE at the global or site level.

QoE is part of the 监控服务器 role; therefore 监控服务器 must be deployed on your Lync Server installation before QoE recording takes effect or any QoE data can be collected.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsQoEConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsQoEConfiguration"}

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
<td><p><em>EnableExternalConsumer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Specifies whether an external consumer is able to receive QoE reports.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnablePurging</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Specifies whether records will be purged after the duration defined in the KeepQoEDataForDays property has elapsed.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableQoE</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Specifies whether QoE records will be collected and saved to the monitoring database.</p>
<p>Note that even if EnableQoE is set to True, QoE data will not be collected unless a 监控服务器 has been deployed and associated with a Registrar pool.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExternalConsumerIssuedCertId</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.BaseTypes.IssuedCertId</p></td>
<td><p>The certificate ID of the certificate that allows access to the external consumer web service.</p></td>
</tr>
<tr class="even">
<td><p><em>ExternalConsumerName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The friendly name of the external consumer of the QoE report.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExternalConsumerURL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The URL of the external consumer to which the QoE reports will be posted.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>The unique identifier of the settings you want to modify. Possible values are global and site:&lt;site name&gt;, where &lt;site name&gt; is the name of the site in your Lync Server deployment to which you want to apply the changes.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>QoESettings</p></td>
<td><p>An object reference to a QoE configuration object. This object must be of type QoESettings and can be retrieved by calling the <strong>Get-CsQoEConfiguration</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>KeepQoEDataForDays</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The number of days QoE data will be stored before being purged from the database. This value is ignored if EnablePurging is set to False.</p>
<p>Must be a value from 1 through 2562.</p></td>
</tr>
<tr class="even">
<td><p><em>PurgeHourOfDay</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The hour of the day that QoE records that have exceeded the number of days specified in the KeepQoEDataForDays property will be purged.</p>
<p>Must be a value 0 through 23, representing the hour of the day. For example, 0 would be midnight, 13 would be 1:00 PM.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.QoE.QoESettings object. Accepts pipelined input of QoE configuration objects.

## Return Types

The **Set-CsQoEConfiguration** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.QoE.QoESettings object.

## 另请参阅

#### 其他资源

[New-CsQoEConfiguration](new-csqoeconfiguration.md)  
[Remove-CsQoEConfiguration](remove-csqoeconfiguration.md)  
[Get-CsQoEConfiguration](get-csqoeconfiguration.md)

