---
title: Set-CsExUmContact
TOCTitle: Set-CsExUmContact
ms:assetid: c0fe0fdc-6fea-4334-8645-24ffd494db07
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412944(v=OCS.15)
ms:contentKeyID: 49314138
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsExUmContact

 

_**上一次修改主题：** 2015-03-09_

为托管的 Exchange 统一消息 (UM) 修改现有自动助理或订阅者访问联系对象。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsExUmContact -Identity <UserIdParameter> [-AutoAttendant <$true | $false>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-DisplayNumber <String>] [-DomainController <Fqdn>] [-Enabled <$true | $false>] [-EnterpriseVoiceEnabled <$true | $false>] [-ExchangeArchivingPolicy <Uninitialized | UseLyncArchivingPolicy | NoArchiving | ArchivingToExchange>] [-PassThru <SwitchParameter>] [-SipAddress <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例将 SIP 地址为 exumsa4@fabrikam.com 的 Exchange UM 联系人的 AutoAttendant 属性设置为 True。我们首先调用 **Get-CsExUmContact** cmdlet 来检索联系对象。（也可能已使用过联系人的 Active Directory 显示名称、联系人的用户主体名称或登录名。）此命令将检索具有所提供的 Identity 的联系人。然后，将该联系人传递到 **Set-CsExUmContact** cmdlet，在其中将该联系人的 AutoAttendant 参数设置为 True。

    Get-CsExUmContact -Identity sip:exumsa4@fabrikam.com | Set-CsExUmContact -AutoAttendant $True

## 示例 2

此示例与示例 1 相同，但不是通过调用 **Get-CsExUmContact** cmdlet 并将对象通过管道传递到 **Set-CsExUmContact** cmdlet 来检索联系人，而是为 **Set-CsExUmContact** cmdlet 提供要修改的联系人的 Identity。请注意 Identity 的格式：在此示例中，使用了联系对象的完全可分辨名称，其中包含一个自动生成的 GUID（在创建联系人时生成）。然后，将联系人的 AutoAttendant 参数设置为 True。

    Set-CsExUmContact -Identity "CN={1bf6208d-2847-45d0-828f-636f14da858b},OU=ExUmContacts,DC=litwareinc,DC=com" -AutoAttendant $True

## 详细说明

Lync Server 与 Exchange UM 结合使用以提供一些与语音相关的功能，包括自动助理和订阅者访问。以托管服务（而不是本地部署）的形式提供 Exchange UM 时，必须使用 Windows PowerShell 创建联系对象以便应用自动助理和订阅者访问功能。可通过调用 **New-CsExUmContact** cmdlet 创建这些对象，并且可在以后使用 **Set-CsExUmContact** cmdlet 对其进行修改。

使用此 cmdlet 最简便的方法通常是首先调用 **Get-CsExUmContact** cmdlet，以检索要修改的联系对象的实例。只需将 **Get-CsExUmContact** cmdlet 命令的输出通过管道传递到 **Set-CsExUmContact** cmdlet，并为要更改的属性分配参数值。（有关详细信息，请参阅本主题中的“示例”部分。）或者，也可以调用 **Set-CsExUmContact** cmdlet，为其传递要修改的联系对象的 Identity。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsExUmContact** cmdlet：RTCUniversalUserAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsExUmContact"}

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
<td><p><em>Identity</em></p></td>
<td><p>必需</p></td>
<td><p>UserIdParameter</p></td>
<td><p>要修改的联系对象的唯一标识符。可以采用下列四种格式之一来指定联系人标识：1) 联系人的 SIP 地址；2) 联系人的用户主体名称 (UPN)；3) 联系人的域名和登录名，格式为“域名\登录名”（如 litwareinc\exum1）；以及 4) 联系人的 Active Directory 显示名称（如 Team Auto Attendant）。</p>
<p>完整数据类型：Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
</tr>
<tr class="even">
<td><p><em>AutoAttendant</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>如果联系对象是自动助理，则将此参数设置为 True。此参数的默认值为 False。</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>此联系人的描述。管理员可使用此描述来识别联系人的类型（自动助理或订阅者访问）、位置、提供者或其他任何用于识别每个 Exchange UM 联系人的目的的信息。</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayNumber</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>联系人的电话号码。每个联系人的显示号码必须是唯一的（两个 Exchange UM 联系人不能使用相同的显示号码）。更改该值还会导致更改 LineURI 属性的值。</p>
<p>此值可以以加号 (+) 开头，并且可以包含任意位数字。第一位数字不能为零。</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>可选</p></td>
<td><p>Fqdn</p></td>
<td><p>用于指定域控制器。如果未指定域控制器，将使用第一个可用的域控制器。</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示该联系人是否已启用 Lync Server。如果此参数设置为 False，将禁用该联系人，且与该联系人关联的自动助理或订阅者访问将不再有效。</p>
<p>如果使用 Enabled 参数禁用了某个帐户，则将保留与该帐户关联的信息（包括分配的托管语音邮件策略）。如果以后使用 Enabled 参数重新启用该帐户，将恢复关联的帐户信息。</p></td>
</tr>
<tr class="even">
<td><p><em>EnterpriseVoiceEnabled</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示该联系人是否已启用企业语音。如果该值设置为 False，则与该联系人关联的自动助理或订阅者访问功能将不再可用。</p></td>
</tr>
<tr class="odd">
<td><p><em>ExchangeArchivingPolicy</em></p></td>
<td><p>可选</p></td>
<td><p>ExchangeArchivingPolicyOptionsEnum</p></td>
<td><p>指定是否存档联系人的即时消息会话。允许的值是：</p>
<p>* Uninitialized</p>
<p>* UseLyncArchivingPolicy</p>
<p>* ArchivingToExchange</p>
<p>* NoArchiving</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>返回命令的结果。默认情况下，此 cmdlet 不生成任何输出。</p></td>
</tr>
<tr class="odd">
<td><p><em>SipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>联系人的 SIP 地址。此地址必须是 Active Directory 域服务中的用户或联系人没有使用过的新地址。</p>
<p>更改该值还会导致更改存储在 OtherIpPhone 属性中的 SIP 地址。</p>
<p>SipAddress 可以用作 <strong>Get-CsExUmContact</strong> cmdlet 命令的 Identity 值来检索特定的联系人。调用该 cmdlet 时，将使用新的 SipAddress；对旧 SIP 地址的查询不会返回对象。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.ADConnect.Schema.OCSADExUmContact 对象。接受通过管道传递的 Exchange UM 联系对象的输入。

## 返回类型

此 cmdlet 修改 Microsoft.Rtc.Management.ADConnect.Schema.OCSADExUmContact 类型的对象。使用 PassThru 参数时，也会返回此类型的对象。

## 另请参阅

#### 其他资源

[New-CsExUmContact](new-csexumcontact.md)  
[Remove-CsExUmContact](remove-csexumcontact.md)  
[Get-CsExUmContact](get-csexumcontact.md)  
[Move-CsExUmContact](move-csexumcontact.md)

