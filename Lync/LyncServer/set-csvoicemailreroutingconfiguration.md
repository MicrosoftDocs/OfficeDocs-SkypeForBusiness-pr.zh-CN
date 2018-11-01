---
title: Set-CsVoicemailReroutingConfiguration
TOCTitle: Set-CsVoicemailReroutingConfiguration
ms:assetid: c16a0d47-318b-46e4-991c-e4842403dbe3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412948(v=OCS.15)
ms:contentKeyID: 49314126
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsVoicemailReroutingConfiguration

 

_**上一次修改主题：** 2015-03-09_

修改提供公用电话交换网 (PSTN) 电话号码以访问 Exchange UM 订阅者访问和自动助理功能的各种设置。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsVoicemailReroutingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsVoicemailReroutingConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AutoAttendantNumber <String>] [-Confirm [<SwitchParameter>]] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-SubscriberAccessNumber <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例启用站点 Redmond1 的语音邮件重新路由配置设置。

    Set-CsVoicemailReroutingConfiguration -Identity site:Redmond1 -Enabled $True

## 示例 2

此示例修改应用于站点 Redmond1 的语音邮件重新路由设置，将订阅者访问的电话号码设置为 +14255551213。

    Set-CsVoicemailReroutingConfiguration -Identity site:Redmond1 -SubscriberAccessNumber "+14255551213"

## 详细说明

使用此 cmdlet 可以在到 Exchange UM 服务器的 IP 连接丢失时修改相应设置，即确定将自动助理和订阅者访问呼叫重新路由至何处的设置。

自动助理和订阅者访问都是 Exchange UM 的功能。自动助理功能为外部呼叫者提供语音识别和电话按键控制（双音多频，简称 DTMF）来导航公司的电话系统，以到达所需部门或员工，或者以消息接收模式接受用户的消息。（建议使用消息接收模式的语音重新路由。）订阅者访问功能使内部用户能够从电话访问其 Microsoft Outlook 邮箱。通过由这些设置提供的号码，呼叫者可以为企业语音用户（AutoAttendantNumber 设置）和检索语音邮件的用户留语音邮件消息，即使从远程站点上部署的 Lync Server 至数据中心的 Exchange UM 的 IP 连接不可用也是如此（SubscriberAccessNumber 设置）。

请注意，除非 Enabled 属性已设置为 True，否则这些设置将不可用。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsVoicemailReroutingConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有 RBAC 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsVoicemailReroutingConfiguration"}

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
<td><p><em>AutoAttendantNumber</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>语音邮件处理尝试应重新路由到的自动助理的电话号码。</p>
<p>提供给此参数的号码必须是一个现有联系对象的 LineUri。</p>
<p>值必须是一个以数字 1 至 9 开头的数，前面可接一个加号 (+)，后跟任意位数的数字。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示当 IP 连接断开时，是否应通过 PSTN 重新路由访问语音邮件的尝试。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsIdentity</p></td>
<td><p>要修改的配置的唯一标识符。对于此 cmdlet，Identity 将为 Global 或 Site:&lt;站点名称&gt;，其中 &lt;站点名称&gt; 是应用设置的站点的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>VoicemailReroutingConfiguration</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p>
<p>此对象的类型必须为 Microsoft.Rtc.Management.WritableConfig.Settings.ExumRouting.VoicemailReroutingConfiguration（可通过调用 <strong>Get-CsVoicemailReroutingConfiguration</strong> cmdlet 进行检索）。</p></td>
</tr>
<tr class="odd">
<td><p><em>SubscriberAccessNumber</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>语音邮件检索尝试应重新路由到的订阅者访问号码。</p>
<p>提供给此参数的号码必须是一个现有联系对象的 LineUri。</p>
<p>值必须是一个以数字 1 至 9 开头的数，前面可接一个加号 (+)，后跟任意位数的数字。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Settings.ExumRouting.VoicemailReroutingConfiguration 对象。接受通过管道传递的语音邮件重新路由配置对象的输入。

## 返回类型

此 cmdlet 不会返回值。它会修改一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.ExumRouting.VoicemailReroutingConfiguration 的对象。

## 另请参阅

#### 其他资源

[New-CsVoicemailReroutingConfiguration](new-csvoicemailreroutingconfiguration.md)  
[Remove-CsVoicemailReroutingConfiguration](remove-csvoicemailreroutingconfiguration.md)  
[Get-CsVoicemailReroutingConfiguration](get-csvoicemailreroutingconfiguration.md)

