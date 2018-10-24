---
title: Remove-CsCdrConfiguration
TOCTitle: Remove-CsCdrConfiguration
ms:assetid: 64352746-a03c-434a-9baf-4d9cd630e9da
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398451(v=OCS.15)
ms:contentKeyID: 49313055
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsCdrConfiguration

 

_**上一次修改主题：** 2015-03-09_

删除指定的呼叫详细信息记录 (CDR) 设置集合。通过 CDR 可以跟踪对等即时消息会话、IP 语音 (VoIP) 呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsCdrConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 使用 **Remove-CsCdrConfiguration** cmdlet 删除分配给站点 Redmond 的 CDR 设置。使用 Identity 参数可确保仅删除分配给指定站点的设置。

    Remove-CsCdrConfiguration -Identity site:Redmond

## 示例 2

示例 2 中显示的命令删除在站点范围分配的所有 CDR 设置。为执行此操作，该命令首先使用 **Get-CsCdrConfiguration** cmdlet 和 Filter 参数检索相应的 CDR 设置；字符串值“site:\*”可确保仅返回 Identity 以字符“site:”开头的。然后，将筛选出的集合通过管道传递到 **Remove-CsCdrConfiguration** cmdlet，后者将删除集合中的所有项。

    Get-CsCdrConfiguration -Filter site:* | Remove-CsCdrConfiguration

## 示例 3

在示例 3 中，将删除 KeepCallDetailForDays 属性小于 30 天的所有 CDR 设置。为了执行此任务，该命令调用不带任何参数的 **Get-CsCdrConfiguration** cmdlet，以便返回组织中当前使用的所有 CDR 设置的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者将仅挑选出 KeepCallDetailForDays 属性小于 30 天的设置。然后，将筛选出的集合通过管道传递到 **Remove-CsCdrConfiguration** cmdlet，后者将删除集合中的每一项。

    Get-CsCdrConfiguration | Where-Object {$_.KeepCallDetailForDays -lt 30} | Remove-CsCdrConfiguration

## 详细说明

呼叫详细信息记录 (CDR) 提供了一种方法，用于跟踪 Lync Server 功能（如 IP 语音 (VoIP) 电话呼叫、即时消息、文件传输、音频/视频 (A/V) 会议和应用程序共享会话）的使用情况。CDR（仅当部署了监控服务时才可用）会保留使用情况信息：它记录的信息包括呼叫中涉及的各方、呼叫的长度以及是否传输了任何文件等。（但是，CDR 并不会记录呼叫自身。）

此外，CDR 还会记录呼叫错误信息：对等会话和会议呼叫的详细诊断数据。

作为管理员，您可以确定是否在组织中使用 CDR。如果已部署了监控服务，则可以轻松启用或禁用 CDR。此外，您可以在全局（在这种情况下 CDR 将在整个组织内启用或禁用），或者以每个站点为基础做出此决定。例如，您可以在 Redmond 站点中使用 CDR，但不在 Paris 站点中使用 CDR。

以后可使用 **Remove-CsCdrConfiguration** cmdlet 删除使用 **New-CsCdrConfiguration** cmdlet 创建的特定于站点的设置。删除特定于站点的设置时，受影响站点的 CDR 将自动由全局 CDR 配置设置进行管理。

还可以对全局 CDR 设置运行 **Remove-CsCdrConfiguration** cmdlet。但是，由于不能删除全局设置，因此只是将其重置为默认值。例如，假设您将全局设置中的 KeepCallDetailForDays 属性值设置为 90。如果针对全局设置运行 **Remove-CsCdrConfiguration** cmdlet，则该属性将重置为其默认值 60。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsCdrConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsCdrConfiguration"}

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
<td><p><em>Identity</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>要删除的 CDR 配置设置的唯一标识符。要“删除”全局设置，请使用以下语法：-Identity global。（请再次注意，您实际上无法删除全局设置，只能将属性重置为其默认值。）要删除站点范围中的设置，请使用类似如下的语法：-Identity site:Redmond。在指定 Identity 时不能使用通配符。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Settings.CallDetailRecording.CdrSettings。**Remove-CsCdrConfiguration** cmdlet 接受通过管道传递的 CDR 配置对象的输入。

## 返回类型

无。但此 cmdlet 会删除 Microsoft.Rtc.Management.WritableConfig.Settings.CallDetailRecording.CdrSettings 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsCdrConfiguration](get-cscdrconfiguration.md)  
[New-CsCdrConfiguration](new-cscdrconfiguration.md)  
[Set-CsCdrConfiguration](set-cscdrconfiguration.md)

