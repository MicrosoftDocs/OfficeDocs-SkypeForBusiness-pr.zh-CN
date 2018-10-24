---
title: Get-CsTenantFederationConfiguration
TOCTitle: Get-CsTenantFederationConfiguration
ms:assetid: e5f836d0-6066-4c23-9594-6e3f1cbd39ef
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994072(v=OCS.15)
ms:contentKeyID: 52061149
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsTenantFederationConfiguration

 

_**上一次修改主题：** 2015-03-09_

返回有关您的 Microsoft Lync Online 租户的联盟配置设置的信息。联盟配置设置用于确定允许您的用户与哪些域（如果有）进行通信。

**Get-CsTenantFederationConfiguration**只能与 Skype for Business Online 一起使用。

## 语法

    Get-CsTenantFederationConfiguration [[-Identity] <XdsIdentity>] [-Tenant <Nullable`1>] [-LocalStore] [-Verbose] Get-CsTenantFederationConfiguration [-Tenant <Nullable`1>] [-Filter <String>] [-LocalStore] [-Verbose]

## 示例

## 示例 1

示例 1 中显示的命令返回租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户的联盟配置信息。可使用类似如下的命令检索租户 ID：

Get-CsTenant | Select-Object TenantID

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

请注意，Tenant 参数是可选的。您还可以使用此语法调用 Get-CsTenantFederationConfiguration：

    Get-CsTenantFederationConfiguration

## 示例 2

在示例 2 中，返回在租户 bf19b7db-6960-41e5-a139-2aa373474354 的联盟允许列表上找到的所有域的信息。（允许列表代表允许租户与其建立联盟的所有域。）为此，命令首先调用 **Get-CsTenantFederationConfiguration** cmdlet 来返回指定租户的联盟信息。然后，将该信息通过管道传递到 **Select-Object** cmdlet，后者会使用 ExpandProperty “展开”属性 AllowedList。展开属性仅意味着以易于阅读的方式显示存储在该属性屏幕中的所有信息。

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" | Select-Object -ExpandProperty AllowedList

## 示例 3

上述命令返回有关组织中当前正在使用的所有租户的联盟配置。为此，该命令首先不带任何参数调用 **Get-CsTenant** cmdlet 以返回所有可用租户的集合。然后，将该集合通过管道传递到 **ForEach-Object** cmdlet。ForEach-Object 将选取集合中的每个租户并调用 **Get-CsTenantFederationConfiguration** cmdlet，此时使用属性值 TenantID（由 **Get-CsTenant** cmdlet 返回）代表租户 ID。

    Get-CsTenant | ForEach-Object {Get-CsTenantFederationConfiguration -Tenant $_.TenantId}

## 示例 4

在示例 4 中，仅返回不允许与公共用户建立联盟的租户的联盟配置信息。为执行此操作，该命令首先不带任何参数调用 **Get-CsTenant** cmdlet，以便返回配置为在组织中使用的所有租户的集合。将该集合通过管道传递到 **ForEach-Object** cmdlet，后者将选取集合中的每个租户，并使用 **Get-CsTenantFederationConfiguration** cmdlet 返回联盟配置信息。 然后，将整组联盟配置信息通过管道传递到 **Where-Object** cmdlet，后者将仅选取 AllowPublicUsers 属性等于 (-eq) $False 的租户。

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Get-CsTenantFederationConfiguration -Tenant $_.TenantId} | Where-Object {$_.AllowPublicUsers -eq $False}

## 详细说明

联盟是一种使用户能够与其他域中的用户交换即时消息和状态信息的服务。通过 Lync Online，管理员可以使用联盟配置设置控制：

  - 用户是否能够与其他域中的人员进行通信，如果可以，他们允许与哪些域进行通信。

  - 用户是否能够与拥有公共即时消息和状态提供商（例如，Windows Live、AOL 和 Yahoo）帐户的人员进行通信。

**Get-CsTenantFederationConfiguration** cmdlet 为管理员提供了一种返回其 Lync Online 租户的联盟信息的方法。此 cmdlet 还可用于查看允许的列表和阻止的列表（用于指定用户可以和不能与之通信的域）。但是，管理员必须使用 **Get-CsTenantPublicProvider** cmdlet 查看允许用户与之进行通信的公共即时消息和状态提供商。

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
<td><p><em>Filter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您能够使用通配符，以便返回租户联盟配置设置的集合。由于每个租户限制为联盟配置设置的单个全局集合，无需使用 Filter 参数。但是，这是 <strong>Get-CsTenantFederationConfiguration</strong> cmdlet 的有效语法：</p>
<p>Get-CsTenantFederationConfiguration –Tenant &quot;bf19b7db-6960-41e5-a139-2aa373474354&quot; –Filter &quot;g*&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>指定要返回的租户联盟配置设置集合。由于每个租户限制为联盟设置的单个全局集合，在调用 <strong>Get-CsTenantFederationConfiguration</strong> cmdlet 时无需包括此参数。如果您选择使用 Identity 参数，则还必须包括 Tenant 参数。例如：</p>
<p>Get-CsTenantFederationConfiguration -Tenant &quot;bf19b7db-6960-41e5-a139-2aa373474354&quot; –Identity &quot;global&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本中检索租户联盟配置数据，而不是从中央管理存储自身中进行检索。</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>可选</p></td>
<td><p>System.Guid</p></td>
<td><p>返回其联盟设置的租户帐户的全局唯一标识符 (GUID)。例如：</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>可以通过运行以下命令来返回每个租户的租户 ID：</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>如果您使用的是 Windows PowerShell 的远程会话，而且只连接到 Skype for Business Online，就不必包括 Tenant 参数。将根据您的连接信息自动为您填充租户 ID。Tenant 参数主要用于混合环境中。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsTenantFederationConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Get-CsTenantFederationConfiguration** cmdlet 返回 Microsoft.Rtc.Management.WritableConfig.Settings.Edge.TenantFederationSettings 对象的实例。

## 另请参阅

#### 其他资源

[Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md)

