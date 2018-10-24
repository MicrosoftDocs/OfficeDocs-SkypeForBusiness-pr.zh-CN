---
title: Set-CsCommonAreaPhone
TOCTitle: Set-CsCommonAreaPhone
ms:assetid: 765ab74c-33ca-4b17-ba15-edb2fe559ebb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398579(v=OCS.15)
ms:contentKeyID: 49313282
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsCommonAreaPhone

 

_**上一次修改主题：** 2015-03-09_

修改由 Lync Server 管理的公用区域电话的属性值。公用区域电话是指位于建筑物大厅、员工休息室或其他可能由多人使用的区域，并供许多不同用户使用的电话。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsCommonAreaPhone -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-Description <String>] [-DisplayName <String>] [-DisplayNumber <String>] [-DomainController <Fqdn>] [-Enabled <$true | $false>] [-EnterpriseVoiceEnabled <$true | $false>] [-ExchangeArchivingPolicy <Uninitialized | UseLyncArchivingPolicy | NoArchiving | ArchivingToExchange>] [-LineURI <String>] [-PassThru <SwitchParameter>] [-SipAddress <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 修改电话号码为 1-425-555-6710 的公用区域电话的 Active Directory 显示名称。为执行此操作，首先调用带有 Filter 参数的 **Get-CsCommonAreaPhone** cmdlet，筛选器值 {LineUri -eq "tel:+14255556710"} 将返回的数据限制为 LineUri 属性等于 tel:+14255556710 的公用区域电话。然后，将返回的对象通过管道传递到 **Set-CsCommonAreaPhone** cmdlet，后者将 DisplayName 属性的值设置为“Employee Lounge”。

    Get-CsCommonAreaPhone -Filter {LineUri -eq "tel:+14255556710"} | Set-CsCommonAreaPhone -DisplayName "Employee Lounge"

## 示例 2

示例 2 中显示的命令启用所有当前配置为在组织中使用的公用区域电话。为完成此任务，该命令首先调用不带任何参数的 **Get-CsCommonAreaPhone** cmdlet，以返回所有公用区域电话的集合。然后，将此集合通过管道传递到 **Set-CsCommonAreaPhone** cmdlet，后者选取集合中的每一项，并将 Enabled 属性设置为 True。

    Get-CsCommonAreaPhone | Set-CsCommonAreaPhone -Enabled $True

## 示例 3

示例 3 为所有未分配 Description 属性值的公用区域电话添加一般性描述。为执行此操作，首先调用带有 Filter 参数的 **Get-CsCommonAreaPhone** cmdlet，筛选器值 {Description -eq $Null} 可确保仅返回 Description 属性等于空值的公用区域电话。然后将筛选出的集合通过管道传递到 **Set-CsCommonAreaPhone** cmdlet，后者将为集合中的每一项分配一般性描述“Common area phone”。

    Get-CsCommonAreaPhone -Filter {Description -eq $Null} | Set-CsCommonAreaPhone -Description "Common area phone"

## 详细说明

公用区域电话是不与个别用户关联的 IP 电话，通常不是位于某人的办公室，而是位于建筑物大厅、餐厅、员工休息室、会议室和其他可能有大量人员聚集的位置。这为管理员的管理工作带来了挑战，因为 Lync Server 中的电话使用通常是使用分配给个别用户的语音策略和拨号计划维护。不会为公用区域电话分配个别用户。

此问题的解决方案之一是为所有公用区域电话创建 Active Directory 联系对象。（可以使用 **New-CsCommonAreaPhone** cmdlet 来创建这些联系对象。）与用户帐户相同，可以为这些联系对象分配策略和语音计划。这样，即使公用区域电话未与个别用户关联，也可以控制这些电话。例如，如果您不希望用户能够转接或寄存来自公用区域电话的呼叫，可以创建禁止呼叫转接和呼叫寄存的语音策略，然后将该策略分配给公用区域电话。（更准确地说，分配给代表公用区域电话的联系对象。）此命令可将语音策略 CommonAreaPhoneVoicePolicy 分配给所有公用区域电话：

Get-CsCommonAreaPhone | Grant-CsVoicePolicy –PolicyName "CommonAreaPhoneVoicePolicy"

**Set-CsCommonAreaPhone** cmdlet 提供了一种修改与公用区域电话相关联的联系对象的属性的方法。此方法的功能之一是使您可以更改联系人的 Active Directory 显示名称或与电话关联的线路统一资源标识符 (URI)。还可以使用 Enabled 参数启用或禁用用于与 Lync Server 一起使用的帐户。

此外，可以使用 CsClientPolicy cmdlet 为公用区域电话配置“hotdesking”。如果电话处于 hotdesked 状态，用户可以使用其 Lync Server 凭据登录到电话。除此之外，这使得用户能够轻松访问其联系人。有关详细信息，请参阅 [Set-CsClientPolicy](set-csclientpolicy.md) cmdlet 的帮助主题。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsCommonAreaPhone** cmdlet：RTCUniversalUserAdmins。可以使用 **Grant-CsOUPermission** cmdlet 分配针对特定站点或特定 Active Directory 组织单位 (OU) 运行此 cmdlet 的权限。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsCommonAreaPhone"}

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
<td><p>公用区域电话的唯一标识符。使用相关联系对象的 Active Directory 可分辨名称标识公用区域电话。默认情况下，公用区域电话使用全局唯一标识符 (GUID) 作为其公用名，这意味着电话的 Identity 通常类似如下：CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com。由此可以得知，使用 <strong>Get-CsCommonAreaPhone</strong> cmdlet，然后将返回的对象通过管道传递到 <strong>Set-CsCommonAreaPhone</strong> cmdlet，更便于检索公用区域电话。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>使您可以修改公用区域电话的 Active Directory 描述属性。这提供了一种提供有关电话的其他信息的方法，例如，可以提供电话出现故障时应与其联系的联系人的详细信息。</p></td>
</tr>
<tr class="even">
<td><p><em>DisplayName</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>使您可以修改公用区域电话的 Active Directory 显示名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayNumber</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>显示在 Lync 中的电话号码。您可以采用所喜欢的任意方式设置 DisplayNumber 属性的格式；例如 1-800-555-1234、1-(800)-555-1234、1.800.555.1234 等。选择显示号码时，请记住，只有可进行规范化的号码才会在公用区域电话的显示屏幕上显示。（规范化是指将号码字符串转换为标准电话号码格式的过程。）如果配置显示号码时，不存在用于所使用电话号码格式的规范化规则，则公用区域电话的显示屏幕将显示 LineUri 属性的值，而不是显示 DisplayNumber 属性的值。</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>可选</p></td>
<td><p>Fqdn</p></td>
<td><p>使您可以连接到指定的域控制器，以便修改联系人信息。若要连接到特定的域控制器，请包含 DomainController 参数，后跟计算机名称（例如 atl-mcs-001）或其完全限定域名 (FQDN)，例如：atl-mcs-001.litwareinc.com。</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示公用区域电话的联系对象是否已启用 Lync Server。</p>
<p>如果使用 Enabled 参数禁用某个联系人，则将保留与该帐户相关的信息（包括分配的策略，以及该联系人是否启用了企业语音、远程呼叫控制和/或语音邮件集成）。如果以后使用 Enabled 参数重新启用该帐户，将恢复关联的帐户信息。</p></td>
</tr>
<tr class="even">
<td><p><em>EnterpriseVoiceEnabled</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示公用区域电话的联系对象是否已启用企业语音、由 Microsoft 提供的 IP 语音 (VoIP) 解决方案。通过企业语音，可以使用 Internet 而不是标准电话网络发出电话呼叫。</p></td>
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
<td><p><em>LineURI</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>公用区域电话的电话号码。应该使用 E.164 格式指定线路统一资源标识符 (URI)，并加上“TEL:”前缀。例如：TEL:+14255551297。应将所有分机号添加到线路 URI 的末尾；例如：TEL:+14255551297;ext=51297。</p></td>
</tr>
<tr class="odd">
<td><p><em>PassThru</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>返回代表公用区域电话的对象。</p></td>
</tr>
<tr class="even">
<td><p><em>SipAddress</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>允许公用区域电话与 SIP 设备（如 Lync）进行通信的唯一标识符。SIP 地址必须以 sip: 作为前缀并包含有效的 SIP 域。例如：sip:bldg14lobby@litwareinc.com。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.ADConnect.Schema.OCSADCommonAreaPhoneContact 对象。

## 返回类型

默认情况下，**Set-CsCommonAreaPhone** cmdlet 不会返回任何对象或值。但是，如果包含 PassThru 参数，则此 cmdlet 将返回 Microsoft.Rtc.Management.ADConnect.Schema.OCSADCommonAreaPhoneContact 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsCommonAreaPhone](get-cscommonareaphone.md)  
[Move-CsCommonAreaPhone](move-cscommonareaphone.md)  
[New-CsCommonAreaPhone](new-cscommonareaphone.md)  
[Remove-CsCommonAreaPhone](remove-cscommonareaphone.md)

