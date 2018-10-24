---
title: Get-CsTenantPublicProvider
TOCTitle: Get-CsTenantPublicProvider
ms:assetid: 0d949ec2-206d-4979-a3be-a5578ae93ed3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994016(v=OCS.15)
ms:contentKeyID: 52060960
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsTenantPublicProvider

 

_**上一次修改主题：** 2015-03-09_

返回指明是否允许 Microsoft Lync Online 用户与使用第三方即时消息和状态提供商（例如，Windows Live、AOL 和 Yahoo）帐户的人员进行通信的信息。

此 cmdlet 只能与 Skype for Business Online 一起使用。

## 语法

    Get-CsTenantPublicProvider -Tenant <String> [-Verbose]

## 示例

## 示例 1

示例 1 中显示的命令返回租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户的公共提供商信息。

    Get-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

请注意，Tenant 参数是可选的。您还可以使用此语法调用 Get-CsTenantPublicProvider：

    Get-CsTenantPublicProvider

## 示例 2

上述命令返回有关分配给租户 bf19b7db-6960-41e5-a139-2aa373474354 的所有公共提供商的状态的详细信息。为此，命令首先使用 **Get-CsTenantPublicProvider** cmdlet 返回指定租户的公共提供商信息。然后，将该信息通过管道传递到 **Select-Object** cmdlet，后者会使用 ExpandProperty 参数“展开”DomainPICStatus 属性的值。展开属性仅意味着以易于阅读的方式显示存储在该属性屏幕中的所有值。

    Get-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" | Select-Object -ExpandProperty DomainPICStatus

与此类似的命令将在 Lync Server 2013 的混合部署中使用。

## 示例 3

示例 3 中显示的命令是示例 2 中所显示命令的变体。但是，在示例 3 中，通过“展开”DomainPICStatus 属性的值返回的公共提供商信息将通过管道传递到 **Where-Object** cmdlet。然后，**Where-Object** cmdlet 仅挑选出 Status 属性设置为 Enabled 的那些提供商。实际结果是仅显示已可供使用的那些公共提供商。

    Get-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" | Select-Object -ExpandProperty DomainPICStatus | Where-Object {$_.Status -eq "Enabled"}

## 详细说明

公共提供商是为普通公众提供 SIP 通信服务的组织。与公共提供商建立联盟关系时，实际上就与任何具有该提供商托管的帐户的用户建立了联盟。例如，如果您与 Windows Live 联盟，则您的用户将能够与具有 Windows Live 即时消息帐户的任何人交换即时消息和状态信息。

Lync Online 为管理员提供配置与以下一个或多个公共即时消息和状态提供商之间联盟的方法：

  - Windows Live

  - AOL

  - Yahoo\!

管理员可以使用 **Get-CsTenantPublicProvider** cmdlet 来确定哪些提供商（如果有）已启用联盟。当调用 **Get-CsTenantPublicProvider** cmdlet 时，您将获得类似于下面这样的信息：

    PublicProviderSet     DomainPicStatus
    ------------------    ------------------------
    True                  {Microsoft.Rtc.Management.Hosted.DomainPICStatus}

PublicProviderSet 属性指定一个或多个公共提供商是否已启用联盟。如果 PublicProviderSet 等于 True，则意味着至少一个提供商已启用联盟；如果 PublicProviderSet 设置为 False，则意味着所有三个公共提供商（Windows Live、AOL 和 Yahoo）都已禁用联盟。要确定每个提供商的实际状态，请使用此命令：

    Get-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" | Select-Object -ExpandProperty DomainPICStatus

请注意，启用公共提供商的状态并不意味着用户可以与拥有该提供商帐户的用户交换即时消息和状态信息。除了与提供商本身启用联盟之外，管理员还必须将联盟配置设置的 AllowPublicUsers 属性设置为 True。如果此属性设置为 False，则无论公共提供商配置设置如何，都不允许与任何公共提供商进行通信。

有关详细信息，请参阅 **Set-CsTenantFederationConfiguration** cmdlet 的帮助主题。

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
<td><p>System.String</p></td>
<td><p>返回其公共提供商设置的租户帐户的全局唯一标识符 (GUID)。例如：</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>可以通过运行以下命令来返回每个租户的租户 ID：</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>如果您使用的是 Windows PowerShell 的远程会话，而且只连接到 Skype for Business Online，就不必包括 Tenant 参数。将根据您的连接信息自动为您填充租户 ID。Tenant 参数主要用于混合环境中。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsTenantPublicProvider** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Get-CsTenantPublicProvider** cmdlet 将返回 Microsoft.Rtc.Management.Hosted.TenantPICStatus 对象的实例。

## 另请参阅

#### 其他资源

[Set-CsTenantPublicProvider](set-cstenantpublicprovider.md)

