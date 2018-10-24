---
title: New-CsMediaConfiguration
TOCTitle: New-CsMediaConfiguration
ms:assetid: 3b60c36f-f824-4948-aa46-6745b40b9641
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425881(v=OCS.15)
ms:contentKeyID: 49312558
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsMediaConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of media settings. These settings can be used to specify such things as the supported level of encryption and the maximum allowed video resolution. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsMediaConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-EnableQoS <$true | $false>] [-EnableSiren <$true | $false>] [-EncryptionLevel <SupportEncryption | RequireEncryption | DoNotSupportEncryption>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-MaxVideoRateAllowed <CIF250K | VGA600K | Hd720p15M>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 uses the **New-CsMediaConfiguration** cmdlet to create a new media configuration with the Identity site:Redmond1. This new configuration requires both parties involved in a multimedia conversation to use encryption. That requirement is put in place by adding the EncryptionLevel parameter and setting the parameter value to RequireEncryption.

    New-CsMediaConfiguration -Identity site:Redmond1 -EncryptionLevel RequireEncryption

## EXAMPLE 2

This example uses the **New-CsMediaConfiguration** cmdlet to create a new media configuration with the Identity MediationServer:pool0.litwareinc.com. This new configuration will have an EnableSiren value of True, which means that Siren is enabled for calls involving this 中介服务器.

    New-CsMediaConfiguration -Identity MediationServer:pool0.litwareinc.com -EnableSiren $True

## Detailed Description

This cmdlet creates a new collection of settings that define behaviors for specific media actions.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsMediaConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsMediaConfiguration"}

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
<td><p>A unique identifier specifying the scope at which this configuration is applied (site or service). A configuration at the site scope would be entered as site:&lt;site name&gt;, such as site:Redmond. A service would be entered as &lt;server role&gt;:&lt;fqdn&gt;, such as MediationServer:pool0.litwareinc.com. A media configuration at the global scope will always exist and cannot be removed, so a new global configuration cannot be created.</p>
<p>Media configurations created at the service scope can be created only for the A/V Conferencing service, 中介服务器, and Application Server.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableQoS</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>QoS monitors the quality of voice signals over a network.</p>
<p>Default: False</p></td>
</tr>
<tr class="even">
<td><p><em>EnableSiren</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>By default, the 中介服务器 does not negotiate Siren as a possible codec for calls between itself and other Lync clients. If this setting is True, Siren will be included as a possible codec for use between the 中介服务器 and other Lync clients.</p>
<p>Default: False</p></td>
</tr>
<tr class="odd">
<td><p><em>EncryptionLevel</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Media.EncryptionLevel</p></td>
<td><p>The level of encryption between unified communications devices.</p>
<p>Valid values:</p>
<p>SupportEncryption - secure real-time transport protocol (SRTP) will be used if it can be negotiated.</p>
<p>RequireEncryption - SRTP must be negotiated.</p>
<p>DoNotSupportEncryption - SRTP must not be used.</p>
<p>Default: RequireEncryption</p></td>
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
<td><p><em>MaxVideoRateAllowed</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Media.MaxVideoRateAllowed</p></td>
<td><p>The maximum rate at which video signals will be transferred at the client endpoints.</p>
<p>Valid values: Hd720p15M, VGA600K, CIF250K</p>
<p>Hd720p15M - High definition, with a resolution of 1280 x 720 and aspect ratio 16:9.</p>
<p>VGA600K - VGA, with a resolution of 640 x 480, 25 fps with the aspect ratio 4:3.</p>
<p>CIF250K - Common Intermediate Format (CIF) video format, 15 fps with a resolution of 352 x 288.</p>
<p>Note that these values are not case sensitive; values will be converted to appropriate casing when the configuration is created.</p>
<p>Default: VGA600K</p></td>
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

Creates an object of type Microsoft.Rtc.Management.WritableConfig.Settings.Media.MediaSettings.

## 另请参阅

#### 其他资源

[Remove-CsMediaConfiguration](remove-csmediaconfiguration.md)  
[Set-CsMediaConfiguration](set-csmediaconfiguration.md)  
[Get-CsMediaConfiguration](get-csmediaconfiguration.md)

