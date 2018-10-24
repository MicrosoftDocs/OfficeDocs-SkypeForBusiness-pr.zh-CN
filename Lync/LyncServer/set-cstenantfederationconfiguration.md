---
title: Set-CsTenantFederationConfiguration
TOCTitle: Set-CsTenantFederationConfiguration
ms:assetid: e13c2f55-7a68-4174-a0da-5eec8c65f64c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994080(v=OCS.15)
ms:contentKeyID: 52061161
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsTenantFederationConfiguration

 

_**上一次修改主题：** 2015-03-09_

管理您的 Microsoft Lync Online 租户的联盟配置设置。这些设置用于确定允许您的用户与哪些域（如果有）进行通信。

**Set-CsTenantFederationConfiguration** cmdlet 只能与 Skype for Business Online 一起使用。

## 语法

    Set-CsTenantFederationConfiguration [[-Identity] <XdsIdentity>] [-Tenant <Nullable`1>] [-AllowedDomains <IAllowedDomainsChoice>] [-BlockedDomains <PSListModifier>] [-AllowFederatedUsers] [-AllowPublicUsers] [-SharedSipAddressSpace] [-Force] [-Verbose] [-WhatIf] [-Confirm]Set-CsTenantFederationConfiguration [-Tenant <Nullable`1>] [-AllowedDomains <IAllowedDomainsChoice>] [-BlockedDomains <PSListModifier>] [-AllowFederatedUsers] [-AllowPublicUsers] [-SharedSipAddressSpace] [-Instance <PSObject>] [-Force] [-Verbose] [-WhatIf] [-Confirm]

## 示例

## 示例 1

示例 1 中显示的命令为租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户禁用公共提供商通信。

    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowPublicUsers $False

请注意，Tenant 参数是可选的。如果不使用该参数，Windows PowerShell 将基于您的连接信息自动插入正确的租户 ID。

## 示例 2

示例 2 显示如何能够为您的组织中的所有租户禁用公共提供商通信。为此，命令首先调用 **Get-CsTenant** cmdlet 以返回所有可用租户的集合。然后将该集合通过管道传递到 **Select-Object** cmdlet，该 cmdlet 仅挑选出集合中每个项目的 TenantId 属性。然后将该集合通过管道传递到 **ForEach-Object** cmdlet。然后，F**orEach-Object** cmdlet 将获取各个租户 ID 并针对该 ID 运行 **Set-CsTenantFederationConfiguration** cmdlet，将各个租户的 AllowPublicUsers 属性设置为 False ($False)。

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantFederationConfiguration -Tenant $_.TenantId -AllowPublicUsers $False}

## 示例 3

在示例 3 中，域 fabrikam.com 被分配为租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户的阻止的域列表上的唯一域。为此，示例中的第一个命令使用 **New-CsEdgeDomainPattern** cmdlet 为 fabrikam.com 创建新的域对象。此域对象存储在名为 $x 的变量中。

示例中的第二个命令使用 **Set-CsTenantFederationConfiguration** cmdlet 更新阻止的域列表。使用 Replace 方法确保现有阻止的域列表将替换为新列表：该列表仅包含域 fabrikam.com。

    $x = New-CsEdgeDomainPattern "fabrikam.com"
    Set-CsTenantFederationConfiguration -Tenant bf19b7db-6960-41e5-a139-2aa373474354 -BlockedDomains @{Replace=$x}

## 示例 4

示例 4 中显示的命令将从租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户阻止的域列表中删除 fabrikam.com。为此，示例中的第一个命令使用 **New-CsEdgeDomainPattern** cmdlet 为 fabrikam.com 创建域对象。生成的域对象存储在名为 $x 的变量中。

然后，示例中的第二个命令使用 **Set-CsTenantFederationConfiguration** cmdlet 和 Remove 方法从指定租户的阻止的域列表中删除 fabrikam.com。

    $x = New-CsEdgeDomainPattern "fabrikam.com"
    Set-CsTenantFederationConfiguration -Tenant bf19b7db-6960-41e5-a139-2aa373474354 -BlockedDomains @{Remove=$x}

## 示例 5

示例 5 中显示的命令将域 fabrikam.com 添加到租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户阻止的域列表中。要添加新的阻止域，示例中的第一个命令使用 **New-CsEdgeDomainPattern** cmdlet 为 fabrikam.com 创建域对象。此对象存储在名为 $x 的变量中。

创建域对象后，第二个命令使用 **Set-CsTenantFederationConfiguration** cmdlet 和 Add 方法将 fabrikam.com 添加到阻止的域列表上已有的任何域。

    $x = New-CsEdgeDomainPattern "fabrikam.com"
    Set-CsTenantFederationConfiguration -Tenant bf19b7db-6960-41e5-a139-2aa373474354 -BlockedDomains @{Add=$x}

## 示例 6

示例 6 显示如何删除分配到指定租户的阻止的域列表的所有域。为此，只需包括 BlockedDomains 参数并将其设置为空值 ($Null)。此命令完成后，租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户的阻止的域列表将被清除。

    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -BlockedDomains $Null

## 详细说明

联盟是一种使用户能够与其他域中的用户交换即时消息和状态信息的服务。通过 Lync Online，管理员可以使用联盟配置设置控制：

  -   
    用户是否能够与其他域中的人员进行通信，如果可以，他们允许与哪些域进行通信。

  -   
    用户是否能够与在公共 IM 和状态提供商（例如，Windows Live、AOL 和 Yahoo）上拥有帐户的人员进行通信。

管理员可以使用 **Set-CsTenantFederationConfiguration** cmdlet 启用和禁用与其他域和公共提供商的联盟。此外，此 cmdlet 可用于明确指定用户可以与其通信的域以及/或者不允许用户与其通信的域。但是，管理员必须使用 **Set-CsTenantPublicProvider** cmdlet 指明用户能够和不能与之进行通信的公共 IM 和状态提供商。

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
<th>必需</th>
<th>类型</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>AllowedDomains</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Edge.IAllowedDomainsChoice</p></td>
<td><p>代表允许用户与其通信的域的域对象（使用 <strong>New-CsEdgeAllowList</strong> cmdlet 或 <strong>New-CsEdgeAllowAllKnownDomains</strong> cmdlet 创建的）。如果使用 <strong>New-CsEdgeAllowAllKnownDomains</strong> cmdlet，则用户可以与阻止的域列表上未出现的任何域进行通信。如果使用 <strong>New-CsEdgeAllowList</strong> cmdlet，则用户只能与已添加到允许的域列表的域进行通信。</p>
<p>请注意，字符串值不能直接传递到 AllowedDomains 参数。相反，您必须使用 <strong>New-CsEdgeAllowList</strong> cmdlet 或 <strong>New-CsEdgeAllowAllKnownDomains</strong> cmdlet 创建对象引用，然后使用对象引用变量作为参数值。</p></td>
</tr>
<tr class="even">
<td><p><em>AllowFederatedUsers</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>当设置为 True（默认值）时，潜在允许用户与其他域中的用户进行通信。如果此属性设置为 False，则不管分配给 AllowedDomains 和 BlockedDomains 属性的值如何，用户都不能与其他域中的用户进行通信。</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowPublicUsers</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>当设置为 True（默认值）时，潜在允许用户与在公共 IM 和状态提供商（如 Windows Live、Yahoo 和 AOL）上拥有帐户的用户进行通信。用户可以实际与其通信的公共提供商集合使用 Set-CsTenantPublicProvider cmdlet 进行管理。</p></td>
</tr>
<tr class="even">
<td><p><em>BlockedDomains</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>如果 AllowedDomains 属性设置为 AllowAllKnownDomains，则允许用户与任何域（出现在阻止的域列表中的那些域除外）中的用户进行通信。如果 AllowedDomains 属性未设置为 AllowAllKnownDomains，则将忽略阻止列表，用户只能与明确添加到允许的域列表的域进行通信。</p></td>
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
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>指定要修改的租户联盟配置设置集合。由于每个租户限制为联盟设置的单个全局集合，在调用 <strong>Set-CsTenantFederationConfiguration</strong> cmdlet 时无需包括此参数。如果您选择使用 Identity 参数，则还必须包括 Tenant 参数。例如：</p>
<p>Set-CsTenantFederationConfiguration -Tenant &quot;bf19b7db-6960-41e5-a139-2aa373474354&quot; –Identity &quot;global&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>SharedSipAddressSpace</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>当设置为 True 时，指明驻留在 Lync Online 上的用户与驻留在 Lync Server 的内部部署版本上的用户使用相同的 SIP 域。默认值为 False，意味着两组用户使用不同的 SIP 域。</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>可选</p></td>
<td><p>System.Guid</p></td>
<td><p>修改其联盟设置的租户帐户的全局唯一标识符 (GUID)。例如：</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>可以通过运行以下命令来返回每个租户的租户 ID：</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>如果您正在使用 Windows PowerShell 的远程会话，并且仅连接到 Skype for Business Online，那么您不必包括 Tenant 参数。相反，将基于您的连接信息自动为您填充租户 ID。 Tenant 参数主要用于混合部署。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述如果执行命令会发生什么情况（无需实际执行命令）。</p></td>
</tr>
</tbody>
</table>


## 输入类型

**Set-CsTenantFederationConfiguration** cmdlet 接受通过管道传递的 Microsoft.Rtc.Management.WritableConfig.Settings.Edge.TenantFederationSettings 对象的实例。

## 返回类型

无。但 **Set-CsTenantFederationConfiguration** cmdlet 会修改 Microsoft.Rtc.Management.WritableConfig.Settings.Edge.TenantFederationSettings 对象的现有实例。

## 另请参阅

#### 其他资源

[Get-CsTenantFederationConfiguration](get-cstenantfederationconfiguration.md)

