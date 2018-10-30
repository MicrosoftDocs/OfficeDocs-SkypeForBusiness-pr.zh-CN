---
title: Set-CsCpsConfiguration
TOCTitle: Set-CsCpsConfiguration
ms:assetid: 9c2c0ad1-12f8-47b6-a7ec-60d91c9685bf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412721(v=OCS.15)
ms:contentKeyID: 49313736
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsCpsConfiguration

 

_**上一次修改主题：** 2015-03-09_

修改现有的呼叫寄存服务设置集合。呼叫寄存是一项允许用户寄存来电的服务。寄存呼叫可将呼叫传输到指定范围中的号码或轨道，然后立即将呼叫置于保持状态。任何人（不只是最初接听电话的人员）无论从任何电话只需输入正确的号码，即可恢复对话。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsCpsConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsCpsConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-CallPickupTimeoutThreshold <TimeSpan>] [-Confirm [<SwitchParameter>]] [-EnableMusicOnHold <$true | $false>] [-Force <SwitchParameter>] [-MaxCallPickupAttempts <Int32>] [-OnTimeoutURI <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令通过将寄存呼叫回拨应答电话的最多次数设置为 2，来修改 Identity 为 site:Redmond1 的呼叫寄存服务配配置。这是通过包含 MaxCallPickupAttempts 参数并将参数值设置为 2 来实现的。

    Set-CsCpsConfiguration -Identity site:Redmond1 -MaxCallPickupAttempts 2

## 示例 2

示例 2 是示例 1 中显示的命令的变体，但在此示例中，会将所有（而不仅是一个）呼叫寄存服务配置的 MaxCallPickupAttempts 属性值都设置为 2。为执行此操作，使用 **Get-CsCpsConfiguration** cmdlet 检索组织中使用的所有呼叫寄存服务设置的集合。然后将此集合通过管道传递到 **Set-CsCpsConfiguration** cmdlet，该 cmdlet 将接收集合中的每一项，并将 MaxCallPickupAttempts 属性的值设置为 2。

    Get-CsCpsConfiguration | Set-CsCpsConfiguration -MaxCallPickupAttempts 2

## 示例 3

此示例通过将寄存呼叫回拨前的等待时间（包含在 CallPickupTimeoutThreshold 属性中）设置为 45 秒来修改站点 Redmond1 的呼叫寄存配置。

    Set-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:00:45

## 详细说明

此 cmdlet 用于修改现有的呼叫寄存服务配置。呼叫寄存服务配置指定呼叫寄存后的事项。例如，如果寄存呼叫在一段时间后仍然无人接听，则会将该呼叫自动转接到其他人，如管理员或响应组。可以将呼叫配置为在一段时间段后响铃，以确保不会将其遗忘。此外，可以将呼叫寄存服务配置为在呼叫寄存时为呼叫者播放呼叫等待音乐。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsCpsConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsCpsConfiguration"}

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
<th>参数</th>
<th>是否必需</th>
<th>类型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>CallPickupTimeoutThreshold</em></p></td>
<td><p>可选</p></td>
<td><p>TimeSpan</p></td>
<td><p>呼叫寄存后到回拨此前应答呼叫的电话之前等待的时间。</p>
<p>必须以 hh:mm:ss（hh = 小时，mm = 分钟，ss = 秒）格式输入时间</p>
<p>最小值：10 秒 (00:00:10)；最大值：10 分钟 (00:10:00)</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableMusicOnHold</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>决定寄存呼叫时是否向呼叫者播放音乐。</p>
<p>Lync Server 附带一个默认的呼叫等待音乐文件。可以使用 <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet 更改此文件（从而更改呼叫寄存时呼叫者听到的音乐）。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示任何本该在进行更改前显示的确认提示。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsIdentity</p></td>
<td><p>要修改的配置的唯一标识符。Identity 指定应用配置的范围，该范围为全局或一个特定的站点（格式为 site:&lt;站点名称&gt;，例如 site:Redmond）。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>呼叫寄存服务设置</p></td>
<td><p>呼叫寄存服务配置对象的对象引用，类型为 Microsoft.Rtc.Management.WritableConfig.Settings.CallParkServiceSettings.CallParkServiceSettings。可通过调用 <strong>Get-CsCpsConfiguration</strong> cmdlet 检索此对象。然后可以更改此对象，并通过此参数将此对象传递回 <strong>Set-CsCpsConfiguration</strong> cmdlet 来保存所做的更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxCallPickupAttempts</em></p></td>
<td><p>可选</p></td>
<td><p>Int32</p></td>
<td><p>在放弃并将寄存呼叫转接到回退统一资源标识符 (URI) 之前该呼叫回拨应答电话的次数。通过 OnTimeoutURI 参数设置回退 URI。</p>
<p>最小值：1；最大值：10</p></td>
</tr>
<tr class="even">
<td><p><em>OnTimeoutURI</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>无应答的寄存呼叫将路由到的用户或响应组的 SIP 地址。在尝试了由 MaxCallPickupAttempts 参数定义的回拨次数之后，将对该寄存呼叫进行路由。如果该参数设置为 Null，则将忽略 OnTimeoutURI，并且寄存呼叫将在回拨尝试失败后断开。</p>
<p>值必须为以字符串 sip: 开头的 SIP URI。例如，sip:rgs1@litwareinc.com。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Settings.CallParkServiceSettings.CallParkServiceSettings 对象。接受通过管道传递的呼叫寄存服务配置对象的输入。

## 返回类型

修改一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.CallParkServiceSettings.CallParkServiceSettings 的对象。

## 另请参阅

#### 其他资源

[New-CsCpsConfiguration](new-cscpsconfiguration.md)  
[Remove-CsCpsConfiguration](remove-cscpsconfiguration.md)  
[Get-CsCpsConfiguration](get-cscpsconfiguration.md)  
[Set-CsCallParkServiceMusicOnHoldFile](set-cscallparkservicemusiconholdfile.md)

