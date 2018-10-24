---
title: New-CsEdgeAllowList
TOCTitle: New-CsEdgeAllowList
ms:assetid: 21a6d546-9e03-485c-b7ec-9deb778f2b01
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994023(v=OCS.15)
ms:contentKeyID: 52060985
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsEdgeAllowList

 

_**上一次修改主题：** 2015-03-09_

使管理员能够指定允许其用户与之通信的域。**New-CsEdgeAllowList** cmdlet（只能对 Microsoft Lync Online 使用）必须与 **New-CsEdgeDomainPattern** cmdlet 和 **Set-CsTenantFederationConfiguration** cmdlet 配合使用。

## 语法

    New-CsEdgeAllowList [-AllowedDomain <PSListModifier>] [-Verbose]

## 示例

## 示例 1

示例 1 中所示的命令向租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户的允许的域列表分配域 fabrikam.com。为此，示例中的第一个命令使用 **New-CsEdgeDomainPattern** cmdlet 为 fabrikam.com 创建域对象；此对象存储在名为 $x 的变量中。创建域对象之后，将使用 **New-CsEdgeAllowList** cmdlet 创建一个新的仅包含域 fabrikam.com 的允许列表。

创建允许的域列表之后，示例中的最后命令可以使用 **Set-CsTenantFederationConfiguration** cmdlet 将 fabrikam.com 配置为指定租户的允许的域列表上的唯一域。

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"
    $newAllowList = New-CsEdgeAllowList -AllowedDomain $x
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains $newAllowList

请注意，在混合部署中仅需要 Tenant 参数。如果您仅连接到 Skype for Business Online，则可以忽略 Tenant 参数。

## 示例 2

示例 2 显示您如何能够向允许的域列表添加多个域。这可通过多次调用 **New-CsEdgeDomainPattern** cmdlet（要添加到列表的每个域各一次）并将得到的域对象存储在单独的变量中来实现。然后，使用 AllowedDomain 参数并用逗号分隔变量名称即可将各个变量添加到 **New-CsEdgeAllowList** cmdlet 创建的允许列表：

$newAllowList = New-CsEdgeAllowList -AllowedDomain $x,$y

    $x = New-CsEdgeDomainPattern -Domain "contoso.com"
    $y = New-CsEdgeDomainPattern -Domain "fabrikam.com"
    $newAllowList = New-CsEdgeAllowList -AllowedDomain $x,$y
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains $newAllowList

## 示例 3

在示例 3 中，将从允许的域列表中删除所有域。为此，示例中的第一个命令使用 **New-CsEdgeAllowList** cmdlet 创建允许的域的空列表；这可通过将 AllowedDomain 属性设置为 null 值 ($Null) 来实现。然后，得到的对象引用 ($newAllowList) 将与 **Set-CsTenantFederationConfiguration** cmdlet 一起用于从租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户的允许的域列表中删除所有域。

    $newAllowList = New-CsEdgeAllowList -AllowedDomain $Null
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains $newAllowList

## 详细说明

联盟是一种使用户能够与其他域中的用户交换即时消息和状态信息的服务。使用 Lync Online，管理员可以使用联盟配置设置控制以下各项：

  - 用户是否能够与其他域中的人员进行通信，如果可以，他们允许与哪些域进行通信。

  - 用户是否能够与在公共 IM 和状态提供商（例如，Windows Live、AOL 和 Yahoo）上拥有帐户的人员进行通信

联盟部分地使用允许的域和阻止的域列表进行管理。允许的域列表指定允许用户与之通信的域；阻止的域列表指定不允许用户与之通信的域。默认情况下，用户可以与未出现在阻止的列表上的任何域进行通信。但是，管理员可以修改此默认设置并将通信限制为位于允许的域列表上的域。

Lync Online 不允许您直接修改允许的列表或阻止的列表；例如，您不能使用与此类似的命令，该命令会将代表域名的字符串值传递到允许的域列表：

    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains "fabrikam.com"

您必须使用 **New-CsEdgeAllowAllKnownDomains** cmdlet 或 **New-CsEdgeAllowList** cmdlet 创建域对象，然后将域对象传递到 **Set-CsTenantFederationConfiguration** cmdlet。如果希望允许用户与所有域（阻止的域列表上明确指定的域除外）进行通信，请使用 **New-CsEdgeAllowAllKnownDomains** cmdlet。如果希望将用户通信限制为指定的域集合，请使用 **New-CsEdgeAllowList** cmdlet。在这种情况下，只允许用户与出现在允许的域列表上的域进行通信。

要将单个域 (fabrikam.com) 添加到允许的域列表，您需要使用与下面类似的一组命令：

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"
    $newAllowList = New-CsEdgeAllowList -AllowedDomain $x
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AllowedDomains $newAllowList

当此命令完成执行时，仅允许用户与 fabrikam.com 域中的用户进行通信。

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
<td><p><em>AllowedDomain</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>对要添加到允许的域列表的新域（或一组域）的对象引用。必须使用 <strong>New-CsEdgeDomainPattern</strong> cmdlet 创建域对象引用。可以通过使用逗号分隔对象引用来添加多个域对象。例如：</p>
<p>-AllowedDomain $x,$y</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。 **New-CsEdgeAllowList** cmdlet 不接受通过管道传递的输入。

## 返回类型

**New-CsEdgeAllowList** cmdlet 创建 Microsoft.Rtc.Management.WritableConfig.Settings.Edge.AllowList 对象的新实例。

## 另请参阅

#### 其他资源

[New-CsEdgeAllowAllKnownDomains](new-csedgeallowallknowndomains.md)  
[New-CsEdgeDomainPattern](new-csedgedomainpattern.md)  
[Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md)

