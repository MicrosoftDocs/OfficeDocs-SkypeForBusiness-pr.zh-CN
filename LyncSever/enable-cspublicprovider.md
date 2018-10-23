---
title: Enable-CsPublicProvider
TOCTitle: Enable-CsPublicProvider
ms:assetid: 98370dfd-9a53-41a8-a1f3-bb7a516c3c5e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398780(v=OCS.15)
ms:contentKeyID: 49313691
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enable-CsPublicProvider

 

_**上一次修改主题：** 2015-03-09_

启用配置为在组织中使用的公共提供商。公共提供商是向普通公众提供即时消息、状态和相关服务的组织。Lync Server 附带了三个已配置但尚未启用的公共提供商：Yahoo\!、AIM (AOL) 和 Messenger (MSN)。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Enable-CsPublicProvider [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Enable-CsPublicProvider [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令启用 Identity 为 MSN 的公共提供商。如果已启用 Messenger，则该命令将返回一个错误。

    Enable-CsPublicProvider -Identity "Messenger"

## 示例 2

示例 2 启用当前已禁用的所有公共提供商。为了执行此任务，该命令首先使用 **Get-CsPublicProvider** cmdlet 返回配置为在组织中使用的所有公共提供商的集合。将此集合通过管道传递到 **Where-Object** cmdlet，该 cmdlet 将仅选择 Enabled 属性等于 False 的提供商。然后，将筛选出的集合通过管道传递到 **Enable-CsPublicProvider** cmdlet，后者会启用集合中的每一个提供商。

    Get-CsPublicProvider | Where-Object {$_.Enabled -eq $False} | Enable-CsPublicProvider

## 示例 3

示例 3 启用当前未启用的所有公共提供商，条件是这些提供商的验证级别设置为 AlwaysVerifiable。为执行此操作，该命令首先调用 **Get-CsPublicProvider** cmdlet 返回组织中当前使用的所有公共提供商的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者会仅挑选满足以下两个条件的提供商：1) VerificationLevel 属性等于 AlwaysVerifiable；以及 2) Enabled 属性等于 False。（运算符 -and 向 **Where-Object** 说明，必须选择满足所有指定条件的对象。）然后，将筛选出的集合通过管道传递到 **Enable-CsPublicProvider** cmdlet，后者会启用集合中的每一个提供商。

    Get-CsPublicProvider | Where-Object {$_.VerificationLevel -eq "AlwaysVerifiable" -and $_.Enabled -eq $False} | Enable-CsPublicProvider

## 详细说明

联盟是两个组织间建立信任关系以促进沟通的一种途径。建立联盟之后，两个组织中的用户可以相互发送即时消息，订阅状态通知以及使用 Lync 2013 等 SIP 应用程序进行彼此通信。Lync Server 允许建立三种类型的联盟：1) 在您的组织与其他组织之间直接建立联盟；2) 在您的组织与公共提供商之间建立联盟；以及 3) 在您的组织与第三方宿主提供商之间建立联盟。

公共提供商是一种向公众提供 SIP 通信服务的组织。与公共提供商建立联盟关系时，实际上就与任何具有该提供商托管的帐户的用户建立了联盟。例如，如果您与 Messenger (MSN) 联盟，则您的用户将能够与具有 MSN Messenger 即时消息帐户的任何人交换即时消息和状态信息。

为与公共提供商联盟，需要创建并启用一个新的公共提供商。（此外，公共提供商还需要与您建立联盟关系。）公共提供商可以在创建时启用，也可以在创建之后使用 **Enable-CsPublicProvider** cmdlet 来启用。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Enable-CsPublicProvider** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Enable-CsPublicProvider"}

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
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要启用的公共提供商的唯一标识符。Identity 通常是提供相关服务的网站名称（例如 Yahoo!、AOL 和 MSN）。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>DisplayPublicProvider 对象</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayPublicProvider 对象。**Enable-CsPublicProvider** cmdlet 接受通过管道传递的公共提供商对象的实例。

## 返回类型

无。但此 cmdlet 会启用 Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayPublicProvider 对象的实例。

## 另请参阅

#### 其他资源

[Disable-CsPublicProvider](disable-cspublicprovider.md)  
[Get-CsPublicProvider](get-cspublicprovider.md)  
[New-CsPublicProvider](new-cspublicprovider.md)  
[Remove-CsPublicProvider](remove-cspublicprovider.md)  
[Set-CsPublicProvider](set-cspublicprovider.md)

