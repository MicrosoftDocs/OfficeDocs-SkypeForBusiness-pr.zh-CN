---
title: Remove-CsConferenceDirectory
TOCTitle: Remove-CsConferenceDirectory
ms:assetid: c2c62a14-f3f3-472f-bf91-1fcea9e45425
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412961(v=OCS.15)
ms:contentKeyID: 49314147
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsConferenceDirectory

 

_**上一次修改主题：** 2015-03-09_

删除现有会议目录。会议目录用于帮助电话拨入式会议用户查找会议信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令删除 Identity 为 2 的会议目录。

    Remove-CsConferenceDirectory -Identity 2

## 示例 2

示例 2 删除 UserServer:atl-cs-001.litwareinc.com 服务上的所有会议目录。为执行此操作，该命令首先调用不带任何参数的 **Get-CsConferenceDirectory** cmdlet；这将返回组织中当前使用的所有会议目录的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者会仅挑选在服务 UserServer:atl-cs-001.litwareinc.com 上托管的目录。接下来，再将筛选出的集合通过管道传递到 **Remove-CsConferenceDirectory** cmdlet 并由其删除。

    Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "UserServer:atl-cs-001.litwareinc.com"} | Remove-CsConferenceDirectory

## 详细说明

在创建电话拨入式会议统一资源标识符 (URI) 时，将会为这些 URI 分配唯一的 SIP 地址。但是，SIP 地址很难转换为无法识别 SIP 的设备；例如，公用电话交换网 (PSTN) 电话不能转换 SIP 地址。因此，Lync Server 使用会议目录作为一种方法，以帮助这些设备查找并连接到电话拨入式会议。这是通过创建与每个电话拨入式会议 URI 关联，并由整数值而非 SIP URI 标识的 SIP 会议目录实现的。PSTN 电话和其他设备随后可在连接会议时使用这些数字（而非 SIP URI）；用户在连接电话拨入式会议时输入的 PSTN 会议标识中即包括目录编号。

会议目录是使用 **New-CsConferenceDirectory** cmdlet 创建的。有时，您可能需要删除其中一个或多个目录；例如，您可能需要停用托管这些目录的池。可以通过调用 **Remove-CsConferenceDirectory** cmdlet 来删除会议目录。请注意，如果需要将目录从一个池移到另一个池，则可通过调用 **Move-CsConferenceDirectory** cmdlet 执行此操作。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsConferenceDirectory** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsConferenceDirectory"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要删除的会议目录的数字标识。</p></td>
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
<td><p>如果存在此参数，请删除会议目录，即使托管该目录的池当前不可用也是如此。默认情况下，如果无法访问对应的池，<strong>Remove-CsConferenceDirectory</strong> cmdlet 将不会删除目录。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.PstnConf.ConferenceDirectories 对象。**Remove-CsConferenceDirectory** cmdlet 接受通过管道传递的会议目录对象的输入。

## 返回类型

无。但 **Removes-CsConferenceDirectory** cmdlet 会删除 Microsoft.Rtc.Management.WritableConfig.Settings.PstnConf.ConferenceDirectories 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsConferenceDirectory](get-csconferencedirectory.md)  
[Move-CsConferenceDirectory](move-csconferencedirectory.md)  
[New-CsConferenceDirectory](new-csconferencedirectory.md)

