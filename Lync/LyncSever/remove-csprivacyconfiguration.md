---
title: Remove-CsPrivacyConfiguration
TOCTitle: Remove-CsPrivacyConfiguration
ms:assetid: 32052c51-953d-4278-9425-306245d297ed
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425821(v=OCS.15)
ms:contentKeyID: 49312428
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsPrivacyConfiguration

 

_**上一次修改主题：** 2015-03-09_

删除现有的隐私配置设置集合。隐私配置设置有助于确定用户向其他用户提供的信息量。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsPrivacyConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 返回分配给 Redmond 站点的隐私配置设置。删除这些设置之后，Redmond 站点中的用户将自动继承全局隐私配置设置。

    Remove-CsPrivacyConfiguration -Identity site:Redmond

## 示例 2

在示例 2 中，将删除在站点范围分配的所有隐私配置设置。为执行此操作，该命令首先调用带 Filter 参数的 **Get-CsPrivacyConfiguration** cmdlet；筛选器值“site:\*”可确保仅返回 Identity 以字符“site”开头的设置。然后，将筛选出的集合通过管道传递到 **Remove-CsPrivacyConfiguration** cmdlet，后者会删除集合中的每一项。

    Get-CsPrivacyConfiguration -Filter "site:*" | Remove-CsPrivacyConfiguration

## 示例 3

示例 3 中显示的命令删除已禁用隐私模式的所有隐私配置设置。为完成此任务，该命令首先调用不带任何参数的 **Get-CsPrivacyConfiguration** cmdlet；这将返回组织中使用的所有隐私配置设置的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者将仅选择 EnablePrivacyMode 属性等于 False 的设置。然后将筛选出的集合通过管道传递到 **Remove-CsPrivacyConfiguration** cmdlet，后者将删除集合中的每一项。

    Get-CsPrivacyConfiguration | Where-Object {$_.EnablePrivacyMode -eq $False} | Remove-CsPrivacyConfiguration

## 详细说明

通过 Lync Server，用户可以与其他人共享大量的状态信息：可以发布自己的照片；可以提供详细的位置信息；可以向组织中的所有人自动提供状态信息（而不是仅向用户联系人列表上的人员提供此信息）。

某些用户会乐于有机会向同事提供此信息；而其他用户可能不愿意共享此数据。（例如，许多人可能对在状态数据中提供其照片犹豫不决。）一般而言，用户可以控制他们将共享（或不共享）的信息；例如，用户可以选中或取消选中某个复选框以便控制是否与他人共享其位置信息。此外，通过隐私配置 cmdlet，管理员可以管理其用户的隐私设置。在某些情况下，管理员可以启用或禁用设置。例如，如果将属性 AutoInitiateContacts 设置为 True，则会将团队成员自动添加到每个用户的联系人列表中；如果将此属性设置为 False，则不会将团队成员自动添加到每个用户的联系人列表中。

在其他情况下，管理员可以在 Lync Server 中配置默认值，同时还向用户授予更改这些值的权限。例如，默认情况下将发布用户的位置数据，但用户有权停止发布位置。通过将 PublishLocationDataByDefault 属性设置为 False，管理员可以更改此行为：此时，默认情况下不会发布位置数据，但用户仍将有权按照自己的意愿发布此数据。

可以在全局范围、站点范围和服务范围（但仅限用户服务器服务）应用隐私配置设置。**Remove-CsPrivacyConfiguration** cmdlet 提供了一种方法，用于删除在站点范围或服务范围配置的设置；例如，如果针对在站点范围配置的设置运行此 cmdlet，则会删除这些设置，并且该站点中用户的隐私设置将由全局集合进行管理。此外，也可以针对全局集合运行 **Remove-CsPrivacyConfiguration** cmdlet；但是，不会删除全局集合。该集合中的所有属性都将重置为其默认值。例如，假设您以前将 EnablePrivacyMode 属性更改为 True。那么如果现在“删除”全局集合，则 EnablePrivacyMode 将还原为其默认值 False。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsPrivacyConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsPrivacyConfiguration"}

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
<td><p>要删除的隐私配置设置的唯一标识符。要删除在站点范围配置的设置，请使用以下类似语法：-Identity site:Redmond。要删除服务级别的设置，请使用以下类似语法：-Identity service:UserServer:atl-cs-001.litwareinc.com。</p>
<p>此外，也可以针对全局设置集合运行 <strong>Remove-CsPrivacyConfiguration</strong> cmdlet。但在这种情况下，将不会删除全局设置，而是会将该集合中的所有属性重置为其默认值。</p></td>
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
<td><p><em>Tenant</em></p></td>
<td><p>可选</p></td>
<td><p>System.Guid</p></td>
<td><p>要删除其隐私配置设置的 Skype for Business Online 租户帐户的全局唯一标识符 (GUID)。例如：</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>通过运行以下命令，可返回每位租户的租户 ID：</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.PrivacyConfiguration 对象。**Remove-CsPrivacyConfiguration** cmdlet 接受通过管道传递的隐私配置对象的输入。

## 返回类型

无。但 **Remove-CsPrivacyConfiguration** cmdlet 会删除 Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.PrivacyConfiguration 对象的现有实例。

## 另请参阅

#### 其他资源

[Get-CsPrivacyConfiguration](get-csprivacyconfiguration.md)  
[New-CsPrivacyConfiguration](new-csprivacyconfiguration.md)  
[Set-CsPrivacyConfiguration](set-csprivacyconfiguration.md)

