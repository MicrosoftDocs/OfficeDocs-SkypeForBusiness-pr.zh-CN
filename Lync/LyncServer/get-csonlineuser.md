---
title: Get-CsOnlineUser
TOCTitle: Get-CsOnlineUser
ms:assetid: 2bfafd70-a7d9-4308-a353-5ecf44249b53
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994026(v=OCS.15)
ms:contentKeyID: 52060982
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsOnlineUser

 

_**上一次修改主题：** 2015-03-09_

返回有关其帐户托管在 Microsoft Lync Online 上的用户的信息。此 cmdlet 只能与 Skype for Business Online 一起使用。

## 语法

    Get-CsOnlineUser [[-Identity] <UserIdParameter>] [-Filter <String>] [-LdapFilter <String>] [-OnOfficeCommunicationServer] [-OnLyncServer] [-UnAssignedUser] [-OU <OUIdParameter>] [-DomainController <Fqdn>] [-Credential <PSCredential>] [-ResultSize <Unlimited`1>] [-Verbose]

## 示例

## 示例 1

示例 1 中显示的命令返回配置为联机用户的所有用户的信息。

    Get-CsOnlineUser

## 示例 2

示例 2 返回了一名联机用户的信息：SIP 地址为“sip:kenmyer@litwareinc.com”的用户。

    Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"

## 示例 3

示例 3 中显示的命令返回已启用 Lync Online 但当前未分配给注册器池的所有联机用户的信息。

    Get-CsOnlineUser -UnassignedUser

## 示例 4

示例 4 使用 Filter 参数将返回的数据限制为已分配每用户存档策略 RedmondArchiving 的联机用户。为执行此操作，使用了筛选值 {ArchivingPolicy -eq "RedmondArchiving"}；该语法将返回的数据限制为 ArchivingPolicy 属性等于 (-eq) "RedmondArchiving" 的用户。

    Get-CsOnlineUser -Filter {ArchivingPolicy -eq "RedmondArchiving"}

## 示例 5

示例 5 仅返回配置为帐户不在 Microsoft Exchange 地址列表中出现的用户帐户的信息。（也就是说，Active Directory 属性 msExchHideFromAddressLists 为 True。）要执行此任务，必须同时包括 Filter 参数和筛选值 {HideFromAddressLists -eq $True}。

    Get-CsOnlineUser -Filter {HideFromAddressLists -eq $True}

## 示例 6

示例 6 中显示的命令返回分配给租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户的所有联机用户的信息。要完成该任务，命令同时包括 Filter 参数和筛选值 {TenantId –eq "bf19b7db-6960-41e5-a139-2aa373474354"}。此筛选器将返回的数据限制为分配给租户“bf19b7db-6960-41e5-a139-2aa373474354”的联机用户。

    Get-CsOnlineUser -Filter {TenantId -eq "bf19b7db-6960-41e5-a139-2aa373474354"}

## 详细说明

**Get-CsOnlineUser** cmdlet 返回有关其帐户托管在 Microsoft Lync Online 上的用户的信息。返回的信息包括标准 Active Directory 帐户信息（例如用户工作所在的部门、其地址和电话号码等）以及 Lync Server 特定信息：**Get-CsOnlineUser** cmdlet 返回有关是否为用户启用了企业语音以及为用户分配了哪个每用户策略（如果有）等类似信息。

请注意，**Get-CsOnlineUser** cmdlet 没有 TenantId 参数；这意味着您不能使用与此类似的命令来将返回的数据限制为在特定 Lync Online 租户中具有帐户的用户：

    Get-CsOnlineUser -TenantId "bf19b7db-6960-41e5-a139-2aa373474354"

但是，如果您有多个 Lync Online 租户，则可以使用 Filter 参数和如下命令从指定租户中返回用户：UNRESOLVED\_TOKEN\_VAL()

    Get-CsOnlineUser -Filter {TenantId -eq "bf19b7db-6960-41e5-a139-2aa373474354"}

该命令将返回的数据限制为属于租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户的用户帐户。如果您不知道租户 ID，则可以使用此命令返回该信息：

    Get-CsTenant

如果您具有混合或“拆分域”部署（也就是说，在某个部署中，一些用户的帐户托管在 Lync Online 上，而其他用户的帐户托管在 Lync Server 的内部部署版本上），请记住，**Get-CsOnlineUser** cmdlet 仅返回 Lync Online 用户的信息。但是，[Get-CsUser](get-csuser.md) cmdlet 将同时返回 Lync Online 用户和本地 Lync Server 用户的信息。如果您希望从 **Get-CsUser** cmdlet 返回的数据中排除 Lync Online 用户，请使用以下命令：

    Get-CsUser -Filter {TenantId -eq "00000000-0000-0000-0000-000000000000"}

根据定义，托管在 Lync Server 的本地版本上的用户的租户 ID 始终等于 00000000-0000-0000-0000-000000000000。托管在 Lync Online 上的用户的租户 ID 等于 00000000-0000-0000-0000-000000000000 以外的其他某个值。

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
<td><p><em>Credential</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>使您可以通过备用凭据运行 <strong>Get-CsOnlineUser</strong> cmdlet。如果登录 Windows 时所用的帐户没有使用用户对象所需的必要权限，则可能需要这样做。</p>
<p>要使用 Credential 参数，必须首先通过 <strong>Get-Credential</strong> cmdlet 创建 PSCredential 对象。有关详细信息，请参阅 <strong>Get-Credential</strong> cmdlet 帮助主题。</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>使您可以连接到指定的域控制器以检索用户信息。要连接到特定的域控制器，请包含 DomainController 参数，后跟完全限定域名 (FQDN)（例如 atl-cs-001.litwareinc.com）。</p></td>
</tr>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您可以通过筛选 Lync Server 特有的属性来限制返回的数据。例如，您可以将返回的数据限定为已分配特定语音策略的用户，或尚未分配特定语音策略的用户。</p>
<p>Filter 参数与 Where-Object cmdlet 使用相同 Windows PowerShell 筛选语法。例如，仅返回已启用企业语音的用户的筛选器语法如下，其中，EnterpriseVoiceEnabled 代表 Active Directory 属性，-eq 代表比较运算符（等于），$True（内置的 Windows PowerShell 变量）代表筛选值：</p>
<p>{EnterpriseVoiceEnabled -eq $True}</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>指示要检索的用户帐户的标识。可以使用下列四种格式之一来指定用户标识：1) 用户的 SIP 地址；2) 用户的用户主体名称 (UPN)；3) 用户的域名和登录名，格式为“域名\登录名”（如 litwareinc\kenmyer）；以及 4) 用户的 Active Directory 显示名称（例如 Ken Myer）。还可以使用用户的 Active Directory 可分辨名称引用用户帐户。</p>
<p>在使用显示名称作为用户标识时，可以使用通配符星号 (*)。例如，标识“* Smith”将返回显示名称以字符串值“Smith”结尾的所有用户。</p></td>
</tr>
<tr class="odd">
<td><p><em>LdapFilter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您可以通过筛选 Active Directory 常规属性（即不是特定于 Lync Server 的属性）来限制返回的数据。例如，您可以将返回数据限制为在特定部门工作的用户，或者拥有指定的经理或其他职务的用户。</p>
<p>LdapFilter 参数在创建筛选器时使用 LDAP 查询语言。例如，仅返回在 Redmond 市工作的用户的筛选器语法如下：&quot;l=Redmond&quot;，其中“l”（小写的 L）代表 Active Directory 属性 (locality)；“=”代表比较运算符（等于）；“Redmond”代表筛选器值。</p></td>
</tr>
<tr class="even">
<td><p><em>OnLyncServer</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>返回驻留在 Lync Server 之上的用户的集合。使用此参数时，将不返回在软件的早期版本上拥有帐户的用户。</p></td>
</tr>
<tr class="odd">
<td><p><em>OnOfficeCommunicationServer</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>返回驻留在 Lync Server 早期版本（例如 Microsoft Office Communications Server 2007 R2）之上的用户的集合。使用此参数时，将不返回在软件当前版本上拥有帐户的用户。</p></td>
</tr>
<tr class="even">
<td><p><em>OU</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.AD.OUIdParameter</p></td>
<td><p>使您可以返回有关特定组织单位 (OU) 或容器中的用户帐户的信息。OU 参数返回来自指定 OU 及其任何子 OU 的数据。例如，如果 Finance OU 有两个子 OU，AccountsPayable 和 AccountsReceivable，则将从这三个 OU 返回用户。</p>
<p>指定 OU 时，请使用此容器的可分辨名称 (DN)，例如：-OU &quot;OU=Finance,dc=litwareinc,dc=com&quot;。要从用户容器返回用户帐户，请使用以下语法：</p>
<p>-OU &quot;cn=Users,dc=litwareinc,dc=com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>ResultSize</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.Unlimited</p></td>
<td><p>使您可以限制 cmdlet 返回的记录数。例如，要返回七个用户（不管林中有多少用户），请包含 ResultSize 参数，并将参数值设置为 7。请注意，无法保证返回哪七个用户。</p>
<p>结果大小可以设置为 0 到 2147483647 之间的任意整数（包含边界值）。如果设置为 0，命令将运行，但是不会返回任何数据。如果将 ResultSize 设置为 7，但是林中仅有三个用户，则此命令将返回这三个用户，操作完成，并且不生成错误。</p></td>
</tr>
<tr class="even">
<td><p><em>UnassignedUser</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>使您可以返回已启用 Lync Online 但当前未分配到注册器池的所有用户的集合。用户除非被分配到注册器池，否则不允许登录。</p></td>
</tr>
</tbody>
</table>


## 输入类型

**Get-CsOnlineUser** cmdlet 接受 Microsoft.Rtc.Management.ADConnect.Schema.OCSADUser 对象的管道实例和代表有效的用户帐户标识的字符串值（例如“sip:kenmyer@litwareinc.com”）。

## 返回类型

**Get-CsOnlineUser** cmdlet 返回 Microsoft.Rtc.Management.ADConnect.Schema.ADOCOnlineUser 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsUser](get-csuser.md)

