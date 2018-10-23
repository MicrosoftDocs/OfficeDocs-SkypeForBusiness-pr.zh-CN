---
title: Remove-CsCpsConfiguration
TOCTitle: Remove-CsCpsConfiguration
ms:assetid: 546343e1-a2e4-4bc0-bf6d-c8ae9bb3e690
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398358(v=OCS.15)
ms:contentKeyID: 49312868
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsCpsConfiguration

 

_**上一次修改主题：** 2015-03-09_

删除现有的呼叫寄存服务配置。呼叫寄存是一项允许用户“寄存”来电的服务。寄存某个呼叫会将该呼叫转接到指定范围或轨道中的一个号码，然后立即将它置于保持状态。任何人（不只是最初接听电话的人员）只需输入正确的号码，即可从任何电话恢复对话。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsCpsConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 使用 **Remove-CsCpsConfiguration** cmdlet 删除 Identity 为 site:Redmond1 的呼叫寄存服务配置。由于标识是唯一的，因此该命令只会删除一个配置。

    Remove-CsCpsConfiguration -Identity site:Redmond1

## 示例 2

在示例 2 中，将删除在站点范围定义的所有呼叫寄存服务配置。为完成此任务，该命令首先使用 **Get-CsCpsConfiguration** cmdlet 和 Filter 参数返回在站点范围定义的所有呼叫寄存服务配置；通配符 site:\* 可确保仅返回 Identity 以字符串值 site: 开头的设置。然后，将筛选出的集合通过管道传递到 **Remove-CsCpsConfiguration** cmdlet，后者会继续删除集合中的每一项。请注意，任何时候从某站点删除呼叫寄存服务设置时，该站点都将自动开始使用在全局范围配置的呼叫寄存服务设置。

    Get-CsCpsConfiguration -Filter site:* | Remove-CsCpsConfiguration

## 详细说明

此 cmdlet 用于删除呼叫寄存服务配置。呼叫寄存服务配置指定呼叫寄存后的事项。例如，如果寄存呼叫在一段时间后仍然无人接听，则会将该呼叫自动转接到其他人，如管理员或响应组。可以将呼叫配置为在一段时间后响铃，以确保不会将其遗忘。此外，可以将呼叫寄存服务配置为在呼叫寄存时为呼叫者播放呼叫等待音乐。

此 cmdlet 可用于删除任何呼叫寄存配置，包括全局配置。但是对于全局配置，实际上并不会删除该配置，而只是将其重置为默认值。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsCpsConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsCpsConfiguration"}

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
<td><p>要删除的呼叫寄存服务配置的唯一标识符。此标识符将为 Global 或 site:&lt;站点名称&gt;，其中 &lt;站点名称&gt; 是应用该配置的站点的名称。</p></td>
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
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.CallParkServiceSettings.CallParkServiceSettings 对象。接受通过管道传递的呼叫寄存服务配置对象的输入。

## 返回类型

删除一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.CallParkServiceSettings.CallParkServiceSettings 的对象。

## 另请参阅

#### 其他资源

[New-CsCpsConfiguration](new-cscpsconfiguration.md)  
[Set-CsCpsConfiguration](set-cscpsconfiguration.md)  
[Get-CsCpsConfiguration](get-cscpsconfiguration.md)  
[Set-CsCallParkServiceMusicOnHoldFile](set-cscallparkservicemusiconholdfile.md)

