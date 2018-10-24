---
title: Remove-CsConferenceDisclaimer
TOCTitle: Remove-CsConferenceDisclaimer
ms:assetid: 196252a1-2526-4944-9064-01d1846f3266
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398243(v=OCS.15)
ms:contentKeyID: 49312144
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsConferenceDisclaimer

 

_**上一次修改主题：** 2015-03-09_

从组织中使用的会议免责声明的标题和正文中清除文本。会议免责声明是一条消息，该消息显示给通过超链接加入会议的用户（例如将会议链接粘贴到诸如 Windows Internet Explorer 等浏览器的用户）。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsConferenceDisclaimer -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 重置全局免责声明的属性值。这意味着免责声明的标题和正文都将设置为空值，从而生成一个空白免责声明。

    Remove-CsConferenceDisclaimer -Identity global

## 详细说明

在配置会议设置时，管理员可在设置中包含一条法律免责声明，以在与会者加入由 Lync Server 托管的会议时向这些人员显示。此免责声明通常用于说明与会议相关的法律和知识产权法。如果用户不同意免责声明中规定的条款，将无法加入会议。请注意，此免责声明只显示给使用超链接加入会议的用户。

Lync Server 允许使用一个会议免责声明全局实例。通过 **Remove-CsConferenceDisclaimer** cmdlet，可以重置会议免责声明：运行此 cmdlet 时，免责声明标题和免责声明正文都将设置为空值。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsConferenceDisclaimer** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsConferenceDisclaimer"}

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
<td><p>要删除的会议免责声明的唯一标识。虽然您只能拥有一个会议免责声明全局实例，但在调用 <strong>Remove-CsConferenceDisclaimer</strong> cmdlet 时仍必须使用 Identity 参数。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConferenceDisclaimer 对象。**Remove-CsConferenceDisclaimer** cmdlet 接受通过管道传递的会议免责声明对象的输入。

## 返回类型

无。但 **Remove-CsConferenceDisclaimer** cmdlet 会将 Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConferenceDisclaimer 对象的现有实例重置为其默认属性值。

## 另请参阅

#### 其他资源

[Get-CsConferenceDisclaimer](get-csconferencedisclaimer.md)  
[Set-CsConferenceDisclaimer](set-csconferencedisclaimer.md)

