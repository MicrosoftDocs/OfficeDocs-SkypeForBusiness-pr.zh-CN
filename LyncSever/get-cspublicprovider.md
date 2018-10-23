---
title: Get-CsPublicProvider
TOCTitle: Get-CsPublicProvider
ms:assetid: c122505d-7209-4dcb-a888-5c73f58fa68a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412945(v=OCS.15)
ms:contentKeyID: 49314139
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPublicProvider

 

_**上一次修改主题：** 2015-03-09_

返回有关配置为在组织中使用的公共提供商的信息。公共提供商是向普通公众提供即时消息、状态和相关服务的组织。Lync Server 附带了三个已配置但尚未启用的公共提供商：Yahoo\!、AIM (AOL) 和 Messenger (MSN)。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsPublicProvider [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsPublicProvider [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

示例 1 中显示的命令返回配置为在组织中使用的所有公共提供商的集合。调用不带任何其他参数的 **Get-CsPublicProvider** cmdlet 将始终返回公共提供商的完整集合。

    Get-CsPublicProvider

## 示例 2

在示例 2 中，返回 Identity 为 Messenger 的所有公共提供商。由于公共提供商（和宿主提供商）的标识必须是唯一的，因此该命令将始终最多返回一项。

    Get-CsPublicProvider -Identity "Messenger"

## 示例 3

示例 3 返回 Identity 以字母 W 开头的所有公共提供商。这是通过包含 Filter 参数和筛选器值“W\*”实现的。

    Get-CsPublicProvider -Filter W*

## 示例 4

示例 4 中显示的命令返回当前已禁用的所有公共提供商的集合。为执行此操作，该命令首先调用 **Get-CsPublicProvider** cmdlet 返回配置为在组织中使用的所有公共提供商的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，该 cmdlet 将仅选择 Enabled 属性等于 False 的提供商。

    Get-CsPublicProvider | Where-Object {$_.Enabled -eq $False}

## 示例 5

示例 5 返回 VerificationLevel 属性设置为 AlwaysUnverifiable 或 UseSourceVerification 的所有公共提供商。（验证级别可设置为 AlwaysUnverifiable、UseSourceVerification 或 AlwaysVerifiable。）为了执行此任务，该命令首先调用 **Get-CsPublicProvider** cmdlet 返回配置为在组织中使用的所有公共提供商的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者将仅挑选出 VerificationLevel 属性不等于 AlwaysVerifiable 的提供商。其最终结果为：只有 VerificationLevel 属性设置为 AlwaysUnverifiable 或 UseSourceVerification 的提供商才被选中。

    Get-CsPublicProvider | Where-Object {$_.VerificationLevel -ne "AlwaysVerifiable"}

## 详细说明

联盟是两个组织间建立信任关系以促进沟通的一种途径。建立联盟之后，两个组织中的用户可以相互发送即时消息，订阅状态通知以及使用 Lync 2013 等 SIP 应用程序进行彼此通信。Lync Server 允许建立三种类型的联盟：1) 在您的组织与其他组织之间直接建立联盟；2) 在您的组织与公共提供商之间建立联盟；以及 3) 在您的组织与第三方宿主提供商之间建立联盟。

公共提供商是一种向公众提供 SIP 通信服务的组织。与公共提供商建立联盟关系时，实际上就与任何具有该提供商托管的帐户的用户建立了联盟。例如，如果您与 Messenger (MSN) 联盟，则您的用户将能够与具有 Messenger 即时消息帐户的任何人交换即时消息和状态信息。

为与公共提供商联盟，需要创建并启用一个新的公共提供商。（此外，公共提供商还需要与您建立联盟关系。）通过 **Get-CsPublicProvider** cmdlet，可以返回有关配置为在组织中使用的公共提供商的信息。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsPublicProvider** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPublicProvider"}

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
<td><p><em>Filter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您可以使用通配符值来返回一个或多个公共提供商。例如，要返回 Identity 以字母 Y 开头的所有公共提供商的集合，请使用以下语法：-Filter &quot;Y*&quot;。要返回其 Identity 中任意位置包含字符串值“Windows”的所有公共提供商的集合，请使用以下语法：-Filter &quot;*Windows*&quot;。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要返回的公共提供商的唯一标识符。Identity 通常是提供相关服务的网站名称（例如 Yahoo!、AOL、MSN 等）。</p>
<p>指定 Identity 时不能使用通配符。要使用通配符返回一个或多个公共提供商，请改用 Filter 参数。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索公共提供商数据。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsPublicProvider** cmdlet 不接受通过管道传递的输入。

## 返回类型

返回 Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayPublicProvider 对象的实例。

## 另请参阅

#### 其他资源

[Disable-CsPublicProvider](disable-cspublicprovider.md)  
[Enable-CsPublicProvider](enable-cspublicprovider.md)  
[New-CsPublicProvider](new-cspublicprovider.md)  
[Remove-CsPublicProvider](remove-cspublicprovider.md)  
[Set-CsPublicProvider](set-cspublicprovider.md)

