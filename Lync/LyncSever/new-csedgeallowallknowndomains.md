---
title: New-CsEdgeAllowAllKnownDomains
TOCTitle: New-CsEdgeAllowAllKnownDomains
ms:assetid: f9416909-c328-41b3-9215-7ebd091b0ca0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994088(v=OCS.15)
ms:contentKeyID: 52061156
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsEdgeAllowAllKnownDomains

 

_**上一次修改主题：** 2015-03-09_

与所有域（阻止的域列表上包括的那些域除外）启用 Microsoft Lync Online 联盟。

此 cmdlet 只能与 Skype for Business Online 一起使用。

## 语法

    New-CsEdgeAllowAllKnownDomains [-Verbose]

## 示例

## 示例 1

示例 1 中显示的两个命令配置 Identity 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户的联盟设置以允许所有已知域。为此，示例中的第一个命令使用 **New-CsEdgeAllowAllKnownDomains** cmdlet 创建 Microsoft.Rtc.Management.WritableConfig.Settings.Edge.AllowAllKnownDomains 对象的实例；此实例存储在名为 $x 的变量中。在第二个示例中，**Set-CsTenantFederationConfiguration** cmdlet 带 AllowedDomains 参数调用；使用 $x 作为参数值可将联盟设置配置为允许所有已知域。

    $x = New-CsEdgeAllowAllKnownDomains
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains $x

## 示例 2

示例 2 说明如何将您的所有租户配置为与阻止的域列表上未明确显示的所有域进行通信。为此，示例中的第一个命令使用 **New-CsEdgeAllowAllKnownDomains** cmdlet 创建 AllowAllKnownDomains 对象的实例；该对象存储在名为 $x 的变量中。

该示例中的第二个命令使用 **Get-CsTenant** cmdlet 返回所有可用租户的集合。然后，将此集合通过管道传递到 **ForEach-Object** cmdlet。接下来，**ForEach-Object** cmdlet 将针对集合中的每个租户运行 **Set-CsTenantFederationConfiguration** cmdlet，以将 AllowedDomains 属性配置为允许所有已知域。

    $x = New-CsEdgeAllowAllKnownDomains
    Get-CsTenant | ForEach-Object {Set-CsTenantFederationConfiguration -Tenant $_.TenantID -AllowedDomains $x}

## 详细说明

联盟是一种使用户能够与其他域中的用户交换即时消息和状态信息的服务。通过 Lync Online，管理员可以使用联盟配置设置控制：

  - 用户是否能够与其他域中的人员进行通信，如果可以，他们允许与哪些域进行通信。

  - 用户是否能够与拥有公共即时消息和状态提供商（例如，Windows Live、AOL 和 Yahoo）帐户的人员进行通信。

联盟一部分使用允许的域和阻止的域列表进行管理。允许的域列表指定允许用户与之通信的域；阻止的域列表指定不允许用户与之通信的域。默认情况下，用户可以与未出现在阻止的列表上的任何域进行通信。但是，管理员可以修改此默认设置并将通信限制为位于允许的域列表上的域。

Lync Online 不允许您直接修改允许的列表或阻止的列表；例如，您不能使用与此类似的命令，该命令会将代表域名的字符串值传递到允许的域列表：

    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains "fabrikam.com"

您必须使用 **New-CsEdgeAllowAllKnownDomains** cmdlet 或 **New-CsEdgeAllowList** cmdlet 创建域对象，然后将域对象传递到 **Set-CsTenantFederationConfiguration** cmdlet。如果希望允许用户与所有域（阻止的域列表上明确指定的域除外）进行通信，请使用 **New-CsEdgeAllowAllKnownDomains** cmdlet。如果希望将用户通信限制为指定的域集合，请使用 N**ew-CsEdgeAllowList** cmdlet。在这种情况下，只允许用户与出现在允许的域列表上的域进行通信。

要配置与所有已知域的联盟，请使用以下类似的一组命令：

    $x = New-CsEdgeAllowAllKnownDomains
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains $x

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
<td><p>此 cmdlet 仅提供公共 Windows PowerShell 参数。</p></td>
<td><p>不适用</p></td>
<td><p>不适用</p></td>
<td><p>不适用</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**New-CsEdgeAllowAllKnownDomains** cmdlet 不接受通过管道传递的输入。

## 返回类型

**New-CsEdgeAllowAllKnownDomains** cmdlet 创建 Microsoft.Rtc.Management.WritableConfig.Settings.Edge.AllowAllKnownDomains 对象的新实例。

## 另请参阅

#### 其他资源

[New-CsEdgeAllowList](new-csedgeallowlist.md)  
[New-CsEdgeDomainPattern](new-csedgedomainpattern.md)  
[Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md)

