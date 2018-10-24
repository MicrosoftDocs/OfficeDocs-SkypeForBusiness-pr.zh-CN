---
title: New-CsEdgeDomainPattern
TOCTitle: New-CsEdgeDomainPattern
ms:assetid: 653bc148-c22b-4ad4-afdd-17aaeaa299d2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994040(v=OCS.15)
ms:contentKeyID: 52061043
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsEdgeDomainPattern

 

_**上一次修改主题：** 2015-03-09_

用于指定将添加到已启用联盟或已禁用联盟的一组域或从这些域中删除的域。修改允许的或阻止的域列表时，必须使用 **New-CsEdgeDomainPattern** cmdlet。字符串值（例如“fabrikam.com”）无法直接传递到用于管理这些列表的 cmdlet。

**New-CsEdgeDomainPattern**只能与 Skype for Business Online 一起使用。

## 语法

    New-CsEdgeDomainPattern -Domain <String> [-Verbose]

## 示例

## 示例 1

示例 1 说明如何向指定租户的阻止的域列表分配单个域。为执行此操作，示例中的第一个命令为域 fabrikam.com 创建一个域对象；这可通过调用 **New-CsEdgeDomainPattern** cmdlet 并将得到的域对象保存在名为 $x 的变量中实现。然后，第二个命令使用 **Set-CsTenantFederationConfiguration** cmdlet 和 BlockedDomains 参数将 fabrikam.com 配置为租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户阻止的唯一域。

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -BlockedDomains $x

## 详细说明

联盟是一种使用户能够与其他域中的用户交换即时消息和状态信息的服务。通过 Skype for Business Online，管理员可以使用联盟配置设置控制：

  - 用户是否能够与其他域中的人员进行通信，如果可以，他们允许与哪些域进行通信。

  - 用户是否能够与拥有公共即时消息和状态提供商（例如，Windows Live、AOL 和 Yahoo）帐户的人员进行通信。

联盟一部分使用允许的域和阻止的域列表进行管理。允许的域列表指定允许用户与之通信的域；阻止的域列表指定不允许用户与之通信的域。默认情况下，用户可以与未出现在阻止的列表上的任何域进行通信。但是，管理员可以修改此默认设置并将通信限制为位于允许的域列表上的域。

Skype for Business Online 不允许您直接修改允许的列表或阻止的列表；例如，您不能使用与此类似的命令，该命令会将代表域名的字符串值传递到阻止的域列表：

    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -BlockedDomains "fabrikam.com"

相反，您必须使用 **New-CsEdgeDomainPattern** cmdlet 创建域对象，将该域对象存储在某个变量（在此示例中为 $x）中，然后将变量名称传递到阻止的域列表：

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"
    Set-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -BlockedDomains $x

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
<td><p><em>Domain</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>要添加到允许列表的完全限定的域名。例如：</p>
<p>-Domain &quot;fabrikam.com&quot;</p>
<p>请注意，在指定域名时不能使用通配符。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**New-CsEdgeDomainPattern** cmdlet 不接受通过管道传递的输入。

## 返回类型

**New-CsEdgeDomainPattern** cmdlet 创建 Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DomainPattern 对象的新实例。

## 另请参阅

#### 其他资源

[New-CsEdgeAllowAllKnownDomains](new-csedgeallowallknowndomains.md)  
[New-CsEdgeAllowList](new-csedgeallowlist.md)  
[Set-CsTenantFederationConfiguration](set-cstenantfederationconfiguration.md)

