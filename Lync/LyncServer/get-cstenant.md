---
title: Get-CsTenant
TOCTitle: Get-CsTenant
ms:assetid: 7b642117-5ca7-4a5b-bca7-16b0ae694ae2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994044(v=OCS.15)
ms:contentKeyID: 52061059
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsTenant

 

_**上一次修改主题：** 2015-03-09_

返回有关已配置为在您的组织中使用的 Skype for Business Online 租户的信息。租户代表联机用户组。在许多情况下，您可能只需要单个租户。但是，如果不同的用户组的管理需求不同，Skype for Business Online 将针对拥有多个租户的单个组织提供支持。

Get-CsTenant 只能与 Skype for Business Online 一起使用。

## 语法

    Get-CsTenant [[-Identity] <OUIdParameter>] [-Filter <String>] [-ResultSize <Unlimited`1>] [-Verbose]

## 示例

## 示例 1

示例 1 中显示的命令返回有关配置为在组织中使用的所有租户的信息。

    Get-CsTenant

## 示例 2

示例 2 将返回单个租户的信息：标识为“bf19b7db-6960-41e5-a139-2aa373474354”的租户。

    Get-CsTenant -Identity "bf19b7db-6960-41e5-a139-2aa373474354"

## 示例 3

上述命令显示返回单个租户的信息的另一种方法；在此示例中，可通过包括 Filter 参数和筛选器值 {DisplayName –eq "Fabrikam"} 实现。该语法仅返回显示名称为 Fabrikam 的租户的信息。

    Get-CsTenant -Filter {DisplayName -eq "Fabrikam"}

## 示例 4

示例 4 中显示的命令返回 ServiceInstance 等于“LitwareincCommunicationsOnline/San Antonio”的所有租户的信息。为此，该命令将使用 Filter 参数和筛选器值 {ServiceInstance -eq "LitwareincCommunicationsOnline/San Antonio"}。该筛选器值将返回的数据限制为 ServiceInstance 属性等于 (-eq) "LitwareincCommunicationsOnline/San Antonio" 的租户。

    Get-CsTenant -Filter {ServiceInstance -eq "LitwareincCommunicationsOnline/San Antonio"}

## 示例 5

示例 5 返回国家或地区显示名称等于“澳大利亚”的所有租户的信息。这是通过使用 Filter 参数并将参数值设置为 {CountryOrRegionDisplayName -eq "澳大利亚"} 实现的。

    Get-CsTenant -Filter {CountryOrRegionDisplayName -eq "Australia"}

## 详细说明

在 Skype for Business Online 中，租户代表其帐户托管在服务上的用户组。许多组织仅需要单个租户来托管其所有用户帐户。但是，Skype for Business Online 管理通常基于租户执行；这意味着相同租户中的所有用户将拥有相同的语音策略、相同的联盟配置等。如果需要通过一种方式管理某些用户，而通过另一种方式管理其他用户，您可以考虑使用多个租户，每个租户拥有其自己的策略和设置集合。

不管您拥有多少个租户，您都可以使用 **Get-CsTenant** cmdlet 返回有关这些租户的信息。

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
<td><p>使您能够使用 Active Directory 属性返回数据，而不必指定完整的 Active Directory 可分辨名称。例如，要使用租户显示名称检索租户，请使用以下类似语法：</p>
<p>Get-CsTenant –Filter {DisplayName –eq &quot;FabrikamTenant&quot;}</p>
<p>要返回使用 Fabrikam 域的所有租户，请使用此语法：</p>
<p>Get-CsTenant –Filter {Domains –like &quot;*fabrikam*&quot;}</p>
<p>Filter 参数与 Where-Object cmdlet 使用的相同的 Windows PowerShell 筛选语法。</p>
<p>不能在同一个命令中同时使用 Identity 参数和 Filter 参数。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.AD.OUIdParameter</p></td>
<td><p>租户的 Active Directory 可分辨名称。例如：</p>
<p>-Identity &quot;OU=bf19b7db-6960-41e5-a139-2aa373474354,OU=OCS Tenants,dc=litwareinc,dc=com&quot;</p>
<p>如果不包含 Identity 或 Filter 参数，则 <strong>Get-CsTenant</strong> cmdlet 将返回有关您的所有租户的信息。</p></td>
</tr>
<tr class="odd">
<td><p><em>ResultSize</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.Unlimited`1</p></td>
<td><p>用于限制 cmdlet 返回的记录数。例如，要返回 7 个租户（不管林中有多少租户），请包含 ResultSize 参数，并将参数值设置为 7。请注意，无法保证返回哪 7 个用户。</p>
<p>结果大小可以设置为 0 到 2147483647 之间的任意整数（包含边界值）。如果设置为 0，命令将运行，但是不会返回任何数据。如果将租户设置为 7，但是林中仅有 3 个联系人，则此命令将返回这 3 个租户，操作完成，并且不生成错误。</p></td>
</tr>
</tbody>
</table>


## 输入类型

**Get-CsTenant** cmdlet 接受 Microsoft.Rtc.Management.ADConnect.Schema.TenantObject 对象的管道实例和代表 Skype for Business Online 租户标识的字符串值（例如“OU=bf19b7db-6960-41e5-a139-2aa373474354,OU=OCS Tenants,dc=vdomain,dc=com”）。

## 返回类型

**Get-CsTenant** cmdlet 返回 Microsoft.Rtc.Management.ADConnect.Schema.TenantObject 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsOnlineUser](get-csonlineuser.md)

