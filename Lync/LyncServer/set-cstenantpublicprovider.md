---
title: Set-CsTenantPublicProvider
TOCTitle: Set-CsTenantPublicProvider
ms:assetid: 8341d801-bfa1-4c5b-9b80-5d503deebaf7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994047(v=OCS.15)
ms:contentKeyID: 52061055
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsTenantPublicProvider

 

_**上一次修改主题：** 2015-03-09_

启用和禁用与第三方即时消息和状态提供商 Windows Live、AOL 和 Yahoo 的通信。启用时，Microsoft Lync Online 用户将能够与在拥有指定公共提供商帐户的用户交换即时消息和状态信息。

**Set-CsTenantPublicProvider**只能与 Skype for Business Online 一起使用。

## 语法

    Set-CsTenantPublicProvider -Tenant <String> [-Provider <String[]>] [-Verbose] [-WhatIf] [-Confirm]

## 示例

## 示例 1

示例 1 中显示的命令为租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户启用与 Windows Live 的联盟。由于 Windows Live 是指定的唯一提供商，AOL 和 Yahoo 提供商将在命令执行之后被禁用。

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

## 示例 2

示例 2 中启用了两个公共提供商：Windows Live 和 AOL。这意味着将为指定租户禁用唯一 Yahoo 公共提供商。

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive","AOL"

## 示例 3

示例 3 显示如何为给定租户禁用所有公共提供商。这是通过将 Provider 属性设置为空字符串 ("") 实现的。

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider ""

## 示例 4

示例 4 中显示的命令将禁用您的所有 Lync Online 租户的所有公共提供商。为完成此任务，该命令首先使用 **Get-CsTenant** cmdlet 返回所有租户的集合。然后，将此集合通过管道传递到 **ForEach-Object** cmdlet，后者将选取集合中的每个租户，针对每个租户调用 **Set-CsTenantPublicProvider** cmdlet，并禁用所有公共提供商。最后一个任务是通过将 Provider 属性设置为空字符串 ("") 实现的。

    Get-CsTenant | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider ""}

## 详细说明

公共提供商是为普通公众提供 SIP 通信服务的组织。与公共提供商建立联盟关系时，实际上就与任何具有该提供商托管的帐户的用户建立了联盟。例如，如果您与 Windows Live 联盟，则您的用户将能够与具有 Windows Live 即时消息帐户的任何人交换即时消息和状态信息。

Lync Online 为管理员提供配置与以下一个或多个公共即时消息和状态提供商的方法：

  -   
    Windows Live

  -   
    AOL

  -   
    Yahoo\!

**Set-CsTenantPublicProvider** cmdlet 可用于启用或禁用于这些公共提供商的联盟。使用此 cmdlet 时请记住，每次运行 **Set-CsTenantPublicProvider** cmdlet 时都必须指定应启用的所有提供商。例如，假设所有三个提供商都已禁用，您运行此命令：

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

正如您可能期望的那样，将启用 Windows Live 并禁用 AOL 和 Yahoo。

现在，假设您接下来运行此命令：

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "AOL"

该命令将启用 AOL。但是，它还将禁用 Windows Live：因为未作为提供给 Provider 参数的参数值的一部分指定 Windows Live。如果希望启用 AOL 和 Windows Live，您必须在调用 Set-CsTenantPublicProvider 时同时指定 AOL 和 Windows Live：

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "AOL","WindowsLive"

要禁用所有三个提供商的联盟，请将 Provider 属性设置为空字符串 ("")：

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider ""

请注意，启用公共提供商的状态并不意味着用户可以与拥有该提供商帐户的用户交换即时消息和状态信息。除了与提供商本身启用联盟之外，管理员还必须将联盟配置设置的 AllowPublicUsers 属性设置为 True。如果此属性设置为 False，则无论公共提供商配置设置如何，都不允许与任何公共提供商进行通信。

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Tenant</em></p></td>
<td><p>必需</p></td>
<td><p>System.Guid</p></td>
<td><p>修改其公共提供商设置的租户帐户的全局唯一标识符 (GUID)。例如：</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>可以通过运行以下命令来返回每个租户的租户 ID：</p>
<pre><code>Get-CsTenant | Select-Object DisplayName, TenantID</code></pre>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Provider</em></p></td>
<td><p>可选</p></td>
<td><p>System.String[]</p></td>
<td><p>指明允许用户与之通信的公共提供商。有效值是：</p>
<p>* AOL</p>
<p>* WindowsLive</p>
<p>* Yahoo</p>
<p>请注意，当配置公共提供商时，Provider 参数值中包括的任何提供商将启用以供使用，同时该参数值中未包括的任何提供商将被禁用。例如，此语法仅启用 Yahoo，同时禁用 Windows Live 和 AOL：</p>
<p>-Provider &quot;AOL&quot;</p>
<p>可以通过使用逗号分隔提供商名称来启用多个提供商：</p>
<p>-Provider &quot;AOL&quot;,&quot;WindowsLive&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述如果执行命令会发生什么情况（无需实际执行命令）。</p></td>
</tr>
</tbody>
</table>


## 输入类型

**Set-CsTenantPublicProvider** cmdlet 接受通过管道传递的 Microsoft.Rtc.Management.Hosted.TenantPICStatus 对象的实例。

## 返回类型

无。但 **Set-CsTenantPublicProvider** cmdlet 会修改 Microsoft.Rtc.Management.Hosted.TenantPICStatus 对象的现有实例。

## 另请参阅

#### 其他资源

[Get-CsTenantPublicProvider](get-cstenantpublicprovider.md)

