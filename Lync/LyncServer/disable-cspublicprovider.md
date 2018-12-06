---
title: Disable-CsPublicProvider
TOCTitle: Disable-CsPublicProvider
ms:assetid: df1338ea-fe6d-45da-a39c-86108bb54ef5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398984(v=OCS.15)
ms:contentKeyID: 49314476
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Disable-CsPublicProvider

 

_**上一次修改主题：** 2015-03-09_

禁用配置为在组织中使用的公共提供商。公共提供商是向普通公众提供即时消息、状态和相关服务的组织。Lync Server 附带了三个已配置但尚未启用的公共提供商：Yahoo；AIM (AOL) 和 Messenger (MSN)。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Disable-CsPublicProvider [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Disable-CsPublicProvider [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 禁用 Identity 为 Messenger 的公共提供商。如果已禁用 MSN，此命令将返回错误。

    Disable-CsPublicProvider -Identity "Messenger"

## 示例 2

示例 2 禁用当前启用的所有公共提供商。为执行此操作，该命令首先使用 **Get-CsPublicProvider** cmdlet 返回组织中当前正在使用的所有公共提供商的集合。将此集合通过管道传递到 **Where-Object** cmdle，后者将仅挑选出 Enabled 属性等于 True 的提供商。接下来，将筛选出的集合通过管道传递到 **Disable-CsPublicProvider** cmdlet，后者将禁用集合中的每个提供商。

    Get-CsPublicProvider | Where-Object {$_.Enabled -eq $True} | Disable-CsPublicProvider

## 示例 3

示例 3 中显示的命令禁用当前已启用且验证级别设置为 AlwaysVerifiable 的所有公共提供商。为完成此任务，该命令首先调用 **Get-CsPublicProvider** cmdlet 以返回组织中当前正在使用的所有公共提供商的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者会选择满足以下两个条件的提供商：1) VerificationLevel 属性等于 AlwaysVerifiable；以及 2) Enabled 属性等于 True。（运算符 -and 向 **Where-Object** cmdlet 说明，必须选择满足所有指定条件的对象。）然后，将筛选出的集合通过管道传递到 **Disable-CsPublicProvider** cmdlet，后者将禁用此集合中的每个提供商。

    Get-CsPublicProvider | Where-Object {$_.VerificationLevel -ne "AlwaysVerifiable" -and $_.Enabled -eq $True} | Disable-CsPublicProvider

## 详细说明

联盟是两个组织间建立信任关系以促进沟通的一种途径。建立联盟之后，两个组织中的用户可以相互发送即时消息，订阅状态通知以及使用 Lync 2013 等 SIP 应用程序进行彼此通信。Lync Server 允许建立三种类型的联盟：1) 在您的组织与其他组织之间直接建立联盟；2) 在您的组织与公共提供商之间建立联盟；以及 3) 在您的组织与第三方宿主提供商之间建立联盟。

公共提供商是为公众提供会话初始协议 (SIP) 通信服务的组织。当您与某个公共提供商建立联盟关系后，实际上便与具有该提供商所托管的帐户的所有用户都建立了联盟关系。例如，如果您与 Messenger (MSN) 联盟，则您的用户将能够与具有 Messenger 即时消息帐户的任何人交换即时消息和状态信息。

为与公共提供商联盟，需要创建并启用一个新的公共提供商。（此外，公共提供商还需要与您建立联盟关系。）创建公共提供商时，您可以选择启用或禁用该联盟关系。如果启用公共提供商，则组织中的用户将能够与具有公共提供商帐户的用户交换即时消息和状态信息。如果禁用公共提供商，则将暂停与具有公共提供商帐户的用户进行通信的功能，且在重新启用该提供商之前将保持暂停状态。如果需要暂时停止提供商关系，您可以使用 **Disable-CsPublicProvider** cmdlet 来执行此操作。如果您希望一同删除该提供商，请使用 **Remove-CsPublicProvider** cmdlet。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Disable-CsPublicProvider** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Disable-CsPublicProvider"}

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
<td><p>要禁用的公共提供商的唯一标识符。Identity 通常是提供相关服务的网站名称（例如 Yahoo!、AOL、MSN 等）。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayPublicProvider 对象。**Disable-CsPublicProvider** cmdlet 接受通过管道传递的公共提供商对象的实例。

## 返回类型

无。但此 cmdlet 会禁用 Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayPublicProvider 对象的实例。

## 另请参阅

#### 其他资源

[Enable-CsPublicProvider](enable-cspublicprovider.md)  
[Get-CsPublicProvider](get-cspublicprovider.md)  
[New-CsPublicProvider](new-cspublicprovider.md)  
[Remove-CsPublicProvider](remove-cspublicprovider.md)  
[Set-CsPublicProvider](set-cspublicprovider.md)

