---
title: Remove-CsPublicProvider
TOCTitle: Remove-CsPublicProvider
ms:assetid: b9eec2f4-cf36-41b7-8023-67790cc8d4cd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412906(v=OCS.15)
ms:contentKeyID: 49314067
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsPublicProvider

 

_**上一次修改主题：** 2015-03-09_

删除配置为在组织中使用的公共提供商。公共提供商是向普通公众提供即时消息 (IM)、状态和相关服务的组织。Lync Server 附带了三个已配置但尚未启用的公共提供商：Yahoo\!、AIM (AOL) 和 Messenger (MSN)。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsPublicProvider -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 删除 Identity 为 Messenger 的公共提供商。完成此命令后，Messenger 将不再出现在已配置的公共提供商列表中；在这种情况下，重新建立带有 Messenger 的联盟的唯一方法是重新创建提供商。

    Remove-CsPublicProvider -Identity "Messenger"

## 示例 2

示例 2 删除配置为在组织中使用的所有公共提供商。为执行此操作，该命令首先使用 **Get-CsPublicProvider** cmdlet 以返回当前配置为可供使用的所有公共提供商的集合。然后，将此集合通过管道传递到 **Remove-CsPublicProvider** cmdlet，后者将删除集合中的每个提供商。

    Get-CsPublicProvider | Remove-CsPublicProvider

## 示例 3

在示例 3 中，从已配置的公共提供商集合中删除当前禁用的所有公共提供商。为执行此任务，该命令首先使用 **Get-CsPublicProvider** cmdlet 以返回当前配置为可供使用的所有公共提供商的集合。将此集合通过管道传递到 **Where-Object** cmdlet，该 cmdlet 将仅选择 Enabled 属性等于 False 的提供商。然后，将筛选出的集合通过管道传递到 **Remove-CsPublicProvider** cmdlet，后者将删除集合中的所有项。

    Get-CsPublicProvider | Where-Object {$_.Enabled -eq $False} | Remove-CsPublicProvider

## 详细说明

联盟是两个组织间建立信任关系以促进沟通的一种途径。建立联盟之后，两个组织中的用户可以相互发送即时消息，订阅状态通知以及使用 Lync 2013 等 SIP 应用程序进行彼此通信。Lync Server 允许建立三种类型的联盟：1) 在您的组织与其他组织之间直接建立联盟；2) 在您的组织与公共提供商之间建立联盟；以及 3) 在您的组织与第三方宿主提供商之间建立联盟。

公共提供商是一种向公众提供 SIP 通信服务的组织。与公共提供商建立联盟关系时，实际上就与任何具有该提供商托管的帐户的用户建立了联盟。例如，如果您与 Messenger (MSN) 联盟，则您的用户将能够与具有 Messenger 即时消息帐户的任何人交换即时消息和状态信息。

为与公共提供商联盟，需要创建并启用一个新的公共提供商。（此外，公共提供商还需要与您建立联盟关系。）如果您决定稍后终止这种关系，则可以使用 **Remove-CsPublicProvider** cmdlet 删除该公共提供商。删除公共提供商时，会从您的联盟伙伴列表中移除该提供商；在这种情况下，重新建立关系的唯一方法是重新创建提供商。如果要暂时停止关系，请改用 **Disable-CsPublicProvider** cmdlet。禁用公共提供商时，不会从联盟伙伴列表中删除该提供商，而只会将该提供商标记为禁用，并暂停组织与该提供商之间的通信。要重新建立关系，您可以使用 **Enable-CsPublicProvider** cmdlet 重新启用该提供商。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsPublicProvider** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsPublicProvider"}

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
<td><p>要删除的公共提供商的唯一标识符。Identity 通常是提供相关服务的网站名称（例如 Yahoo!、AOL、MSN 等）。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayPublicProvider 对象。**Remove-CsPublicProvider** cmdlet 接受通过管道传递的公共提供商对象的实例。

## 返回类型

无。但此 cmdlet 会删除 Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayPublicProvider 对象的实例。

## 另请参阅

#### 其他资源

[Disable-CsPublicProvider](disable-cspublicprovider.md)  
[Enable-CsPublicProvider](enable-cspublicprovider.md)  
[Get-CsPublicProvider](get-cspublicprovider.md)  
[New-CsPublicProvider](new-cspublicprovider.md)  
[Set-CsPublicProvider](set-cspublicprovider.md)

