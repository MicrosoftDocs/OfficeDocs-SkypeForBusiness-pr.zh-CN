---
title: Get-CsCommonAreaPhone
TOCTitle: Get-CsCommonAreaPhone
ms:assetid: bfb7927b-49a7-4637-a9ff-fd68897efb45
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412934(v=OCS.15)
ms:contentKeyID: 49314115
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsCommonAreaPhone

 

_**上一次修改主题：** 2015-03-09_

返回有关通过使用 Lync Server 管理的公用区域电话的信息。公用区域电话是指位于建筑物大厅、员工休息室或其他可能由多人使用的区域，并供许多不同用户使用的电话。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsCommonAreaPhone [-Identity <UserIdParameter>] [-Credential <PSCredential>] [-DomainController <Fqdn>] [-Filter <String>] [-LdapFilter <String>] [-OU <OUIdParameter>] [-ResultSize <Unlimited>]

## 示例

## 示例 1

示例 1 中显示的命令返回有关配置为在组织中使用的所有公用区域电话的信息。这是通过调用不带任何参数的 **Get-CsCommonAreaPhone** cmdlet 来完成的。

    Get-CsCommonAreaPhone

## 示例 2

在示例 2 中，返回 Active Directory 显示名称为“Building 14 Lobby”的公用区域电话。此任务是通过包含 Filter 参数和筛选器值 {DisplayName -eq "Building 14 Lobby"} 来完成的，该筛选器值将返回对象限制为 DisplayName 属性等于“Building 14 Lobby”的公用区域电话。

    Get-CsCommonAreaPhone -Filter {DisplayName -eq "Building 14 Lobby"}

## 示例 3

示例 3 返回 Active Directory 显示名称以字符“Building 14”开头的所有公用区域电话。为执行此操作，调用带有 Filter 参数且筛选器值为 {DisplayName -like "Building 14\*"} 的 **Get-CsCommonAreaPhone** cmdlet。筛选器值使用运算符 -like 和通配符字符串“Building 14\*”，将返回的数据限制为 DisplayName 属性以“Building 14”开头的电话（例如，“Building 14 Lobby”、“Building 14 Cafeteria”等）。

    Get-CsCommonAreaPhone  -Filter {DisplayName -like "Building 14*"}

## 示例 4

在示例 4 中，返回单个公用区域电话：LineUri 属性等于“tel:+14255551234”的电话。由于 LineUri 必须唯一，因此此命令绝不会返回多项。

    Get-CsCommonAreaPhone  -Filter {LineUri -eq "tel:+14255551234"}

## 示例 5

示例 5 中显示的命令返回所有尚未分配拨号计划的公用区域电话。这是通过使用 Filter 参数和筛选器值 {DialPlan -eq $Null} 来完成的，该筛选器值将返回数据限制为 DialPlan 属性等于空值的电话。如果没有为公用区域电话明确分配拨号计划，那么它将自动使用全局拨号计划或分配给站点的拨号计划（如果存在）。

    Get-CsCommonAreaPhone -Filter {DialPlan -eq $Null}

## 示例 6

示例 6 返回在 Active Directory 域服务的 Telecommunications OU 中具有联系对象的所有公用区域电话的集合。为执行此操作，调用带有 OU 参数的 **Get-CsCommonAreaPhone** cmdlet，参数值将返回的对象限制为在可分辨名称为 ou=Telecommunications,dc=litwareinc,dc=com 的 OU 中具有联系对象的电话。

    Get-CsCommonAreaPhone -OU "ou=Telecommunications,dc=litwareinc,dc=com"

## 详细说明

公用区域电话是不与个别用户关联的 IP 电话，通常不是位于某人的办公室，而是位于建筑物大厅、餐厅、员工休息室、会议室和其他可能有大量人员聚集的位置。这为管理员的管理工作带来了挑战，因为 Lync Server 中的电话使用通常是使用分配给个别用户的语音策略和拨号计划维护。不会为公用区域电话分配个别用户。

解决此挑战的方法是为所有公用区域电话创建 Active Directory 联系对象。（可以使用 **New-CsCommonAreaPhone** cmdlet 来创建这些联系对象。）与用户帐户相同，可以为这些联系对象分配策略和语音计划。这样，即使公用区域电话未与个别用户关联，也可以控制这些电话。例如，如果您不希望用户能够转接或寄存来自公用区域电话的呼叫，可以创建禁止呼叫转接和呼叫寄存的语音策略，然后将该策略分配给公用区域电话。（更准确地说，分配给代表公用区域电话的联系对象。）例如，此命令可将语音策略 CommonAreaPhoneVoicePolicy 分配给所有公用区域电话：

Get-CsCommonAreaPhone | Grant-CsVoicePolicy –PolicyName "CommonAreaPhoneVoicePolicy"

**Get-CsCommonAreaPhone** cmdlet 提供了一种检索有关配置为在组织中使用的公用区域电话的信息的方法。如果调用不带任何参数的 **Get-CsCommonAreaPhone** cmdlet，则此 cmdlet 将返回有关所有公用区域电话的信息。可选参数为您提供了筛选信息的不同方法，例如，可以返回在指定组织单位 (OU) 中具有联系对象的所有公用区域电话，或位于指定建筑物的所有联系对象。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsCommonAreaPhone** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins 和 RTCUniversalReadOnlyAdmins。可以使用 **Grant-CsOUPermission** cmdlet 分配针对特定站点或特定 Active Directory OU 运行此 cmdlet 的权限。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsCommonAreaPhone"}

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
<td><p><em>Credential</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>使您可以通过备用凭据运行 <strong>Get-CsCommonAreaPhone</strong> cmdlet。如果您登录 Windows 时所使用的帐户没有使用联系对象所需的必要权限，则可能需要使用该对象。</p>
<p>要使用 Credential 参数，必须首先通过 <strong>Get-Credential</strong> cmdlet 创建 PSCredential 对象。有关详细信息，请参阅 <strong>Get-Credential</strong> cmdlet 帮助主题。</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>使您可以连接到指定的域控制器，以便检索联系人信息。要连接到特定的域控制器，请包含 DomainController 参数，后跟该计算机的完全限定域名 (FQDN)（例如 atl-cs-001.litwareinc.com）。</p></td>
</tr>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>用于通过筛选特定于 Lync Server 的属性来限制返回的数据。例如，可以将返回数据限制为已分配特定语音策略的公用区域电话联系对象，或尚未分配特定语音策略的联系人。</p>
<p>Filter 参数与 <strong>Where-Object</strong> cmdlet 使用相同的 Windows PowerShell 筛选语法。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>公用区域电话的唯一标识符。使用相关联系对象的 Active Directory 可分辨名称 (DN) 标识公用区域电话。默认情况下，公用区域电话使用全局唯一标识符 (GUID) 作为其公用名，这意味着电话通常会具有类似如下的标识：CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com。</p></td>
</tr>
<tr class="odd">
<td><p><em>LdapFilter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您可以通过筛选 Active Directory 常规属性（即不是特定于 Lync Server 的属性）来限制返回的数据。例如，您可以将返回的数据限制为已分配给特定部门或位于特定建筑物中的联系对象。</p>
<p>LdapFilter 参数在创建筛选器时使用 LDAP 查询语言。例如，仅返回代表雷蒙德市公用区域电话的联系对象的筛选器如下所示：</p>
<p>-LDAPFilter &quot;l=Redmond&quot;</p>
<p>在上述筛选器中，“l”（小写的 L）代表 Active Directory 属性 (locality)；“=”代表比较运算符（等于）；“Redmond”代表筛选器值。</p></td>
</tr>
<tr class="even">
<td><p><em>OU</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.AD.OUIdParameter</p></td>
<td><p>使您可以返回特定 Active Directory 组织单位 (OU) 中的联系对象。OU 参数返回来自指定 OU 及其任何子 OU 的数据。例如，如果 Finance OU 有两个子 OU：AccountsPayable 和 AccountsReceivable，则将从这三个 OU 返回公用区域电话信息。</p>
<p>指定 OU 时，请使用此容器的可分辨名称，例如：-OU &quot;OU=Finance,dc=litwareinc,dc=com&quot;。</p></td>
</tr>
<tr class="odd">
<td><p><em>ResultSize</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.Unlimited</p></td>
<td><p>使您可以限制命令返回的记录数。例如，要返回七个公用区域电话（不管林中有多少公用区域电话），请包含 ResultSize 参数，并将参数值设置为 7。请注意，无法保证返回哪七个电话。如果将 ResultSize 设置为 7，但是林中仅有三个公用区域电话，则此命令将返回这三个电话，操作完成，并且不生成错误。</p>
<p>结果大小可以设置为 0 到 2147483647 之间的任意整数（包含边界值）。如果设置为 0，命令将运行，但是不会返回任何数据。</p></td>
</tr>
</tbody>
</table>


## 输入类型

字符串。**Get-CsCommonAreaPhone** cmdlet 接受通过管道传递的字符串值，代表公用区域电话的标识。

## 返回类型

**Get-CsCommonAreaPhone** cmdlet 返回 Microsoft.Rtc.Management.ADConnect.Schema.OCSADCommonAreaPhoneContact 对象的实例。

## 另请参阅

#### 其他资源

[Move-CsCommonAreaPhone](move-cscommonareaphone.md)  
[New-CsCommonAreaPhone](new-cscommonareaphone.md)  
[Remove-CsCommonAreaPhone](remove-cscommonareaphone.md)  
[Set-CsCommonAreaPhone](set-cscommonareaphone.md)

