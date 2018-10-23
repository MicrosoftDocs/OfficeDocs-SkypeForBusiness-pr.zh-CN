---
title: New-CsConferenceDirectory
TOCTitle: New-CsConferenceDirectory
ms:assetid: fd5a4369-10cd-4337-94df-51bcaee4fde9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413080(v=OCS.15)
ms:contentKeyID: 49314856
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsConferenceDirectory

 

_**上一次修改主题：** 2015-03-09_

创建在组织中使用的新会议目录。会议目录用于帮助电话拨入式会议用户查找会议信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsConferenceDirectory -HomePool <String> -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

创建 Identity 为 42 的新会议目录。将在池 atl-cs-001.litwareinc.com 中托管此目录。

    New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

## 详细说明

在创建电话拨入式会议统一资源标识符 (URI) 时，将会为这些 URI 分配唯一的 SIP 地址。但是，SIP 地址很难转换为无法识别 SIP 的设备；例如，公用电话交换网 (PSTN) 电话不能转换 SIP 地址。因此，Lync Server 使用会议目录作为一种方法，以帮助这些设备查找并连接到电话拨入式会议。这是通过创建与每个电话拨入式会议 URI 关联，并由整数值而非 SIP URI 标识的 SIP 会议目录实现的。PSTN 电话和其他设备随后可在连接会议时使用这些数字（而非 SIP URI）；用户在连接电话拨入式会议时输入的 PSTN 会议标识中即包括目录编号。

可以通过调用 **New-CsConferenceDirectory** cmdlet 创建新的会议目录。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsConferenceDirectory** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsConferenceDirectory"}

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
<td><p><em>HomePool</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>将托管新会议目录的注册器池的完全限定域名 (FQDN)。例如：-Identity atl-cs-001.litwareinc.com。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>新会议目录的唯一数字标识符。标识可以是介于 0 和 9999 之间（包含边界值）的任意整数值，但是必须唯一。（例如，不能存在两个 Identity 为 575 的目录。）创建新目录时，不需要遵循数字顺序。例如，可以先创建 Identity 为 999 的目录，再创建 Identity 为 2 的目录，再创建 Identity 为 438 的目录等。</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**New-CsConferenceDirectory** cmdlet 不接受通过管道传递的输入。

## 返回类型

创建 Microsoft.Rtc.Management.WritableConfig.Settings.PstnConf.ConferenceDirectories 对象的新实例。

## 另请参阅

#### 其他资源

[Get-CsConferenceDirectory](get-csconferencedirectory.md)  
[Move-CsConferenceDirectory](move-csconferencedirectory.md)  
[Remove-CsConferenceDirectory](remove-csconferencedirectory.md)

