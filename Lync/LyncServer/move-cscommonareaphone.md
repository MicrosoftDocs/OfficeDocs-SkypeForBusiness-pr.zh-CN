---
title: Move-CsCommonAreaPhone
TOCTitle: Move-CsCommonAreaPhone
ms:assetid: af5f832c-1be9-4495-ba1a-c10ca50d7b29
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412837(v=OCS.15)
ms:contentKeyID: 49313930
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Move-CsCommonAreaPhone

 

_**上一次修改主题：** 2015-04-02_

将一个或多个公用区域电话移至新的注册器池。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Move-CsCommonAreaPhone -Identity <UserIdParameter> -Target <Fqdn> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-IgnoreBackendStoreException <SwitchParameter>] [-PassThru <SwitchParameter>] [-ProxyPool <Fqdn>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令将 Identity 为 CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com 的公用区域电话移至注册器池 atl-cs-001.litwareinc.com。

    Move-CsCommonAreaPhone -Identity "CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com" -Target atl-cs-001.litwareinc.com

## 示例 2

在示例 2 中，将 Active Directory 显示名称为“Building 31 Cafeteria”的公用区域电话移至注册器池 atl-cs-001.litwareinc.com。为执行此操作，首先调用不带任何参数的 **Get-CsCommonAreaPhone** cmdlet，以返回组织中当前使用的所有公用区域电话的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者会仅挑选 DisplayName 属性等于“Building 31 Cafeteria”的电话。接下来，将筛选出的集合通过管道传递到 **Move-CsCommonAreaPhone** cmdlet，后者会将集合中的每个电话都移至 atl-cs-001.litwareinc.com。

    Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -eq "Building 31 Cafeteria"} | Move-CsCommonAreaPhone -Target atl-cs-001.litwareinc.com

## 示例 3

示例 3 将注册器池 dublin-cs-001.litwareinc.com 当前托管的所有公用区域电话移至注册器池 atl-cs-001.litwareinc.com。为执行此任务，该命令首先调用不带任何参数的 **Get-CsCommonAreaPhone** cmdlet；这将返回配置为在组织中使用的所有公用区域电话的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者会仅挑选 RegistrarPool 等于 dublin-cs-001.litwareinc.com 的所有公用区域电话。接下来，将此集合通过管道传递到 **Move-CsCommonAreaPhone** cmdlet，后者会将集合中的每个电话都移至新的注册器池 atl-cs-001.litwareinc.com。

    Get-CsCommonAreaPhone | Where-Object {$_.RegistrarPool -match "dublin-cs-001.litwareinc.com"} | Move-CsCommonAreaPhone -Target atl-cs-001.litwareinc.com

## 示例 4

示例 4 是示例 3 中显示的命令的变体。但在此示例中，公用区域电话不仅移至新的注册器池，还分配了新的每用户语音策略。为执行此操作，调用 **Move-CsCommonAreaPhone** cmdlet 时加入了 PassThru 参数，以便通过管道传递公用区域电话对象。（默认情况下，**Move-CsCommonAreaPhone** cmdlet 不会通过管道传递对象。）移动电话之后，电话对象将通过管道传递到 **Grant-CsVoicePolicy** cmdlet，后者会将语音策略 AtlantaVoicePolicy 分配给新移动的每个电话。

    Get-CsCommonAreaPhone | Where-Object {$_.RegistrarPool -match "dublin-cs-001.litwareinc.com"} | Move-CsCommonAreaPhone -Target atl-cs-001.litwareinc.com -PassThru | Grant-CsVoicePolicy -PolicyName AtlantaVoicePolicy

## 详细说明

公用区域电话是不与个别用户关联的 IP 电话，通常不是位于某人的办公室，而是位于建筑物大厅、餐厅、员工休息室、会议室和其他可能有大量人员聚集的位置。这为管理员的管理工作带来了挑战，因为 Lync Server 中的电话使用通常是使用分配给个别用户的语音策略和拨号计划维护。不会为公用区域电话分配个别用户。

解决此挑战的方法是为所有公用区域电话创建 Active Directory 联系对象。（可以使用 **New-CsCommonAreaPhone** cmdlet 来创建这些联系对象。）与用户帐户相同，可以为这些联系对象分配策略和语音计划。这样，即使公用区域电话未与个别用户关联，也可以控制这些电话。例如，如果您不希望用户能够转接或寄存来自公用区域电话的呼叫，可以创建禁止呼叫转接和呼叫寄存的语音策略，然后将该策略分配给公用区域电话。（更准确地说，分配给代表公用区域电话的联系对象。）

通过 **Move-CsCommonAreaPhone** cmdlet，可以将现有的公用区域电话移至新的注册器池。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Move-CsCommonAreaPhone** cmdlet：RTCUniversalUserAdmins。可以使用 **Grant-CsOUPermission** cmdlet 分配针对特定站点或特定 Active Directory 组织单位 (OU) 运行此 cmdlet 的权限。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Move-CsCommonAreaPhone"}

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
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>公用区域电话的唯一标识符。使用相关联系对象的 Active Directory 可分辨名称标识公用区域电话。默认情况下，公用区域电话使用全局唯一标识符 (GUID) 作为其公用名，这意味着电话通常会具有类似如下的标识：CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com。</p></td>
</tr>
<tr class="even">
<td><p><em>Target</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>应移动公用区域电话的注册器池的完全限定域名 (FQDN)；例如：atl-cs-001.litwareinc.com。除了注册器池以外，目标还可以是宿主提供商的 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>使您可以连接到指定的域控制器，以便移动公用区域电话。要连接到特定的域控制器，请包含 DomainController 参数，后跟计算机名称（例如 atl-cs-001）或其 FQDN（例如 atl-cs-001.litwareinc.com）。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>如果存在此参数，则将移动公用区域电话但会删除所有相关数据（例如分配给该设备的策略）。如果不存在，将同时移动电话和相关数据。</p></td>
</tr>
<tr class="even">
<td><p><em>IgnoreBackendStoreException</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>如果存在此参数，会指示计算机忽略后端数据库可能出现的任何错误，并尝试移动公用区域电话而不考虑这些错误。</p></td>
</tr>
<tr class="odd">
<td><p><em>PassThru</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>使您可以通过管道传递用户对象（代表要移动的用户帐户）。默认情况下，<strong>Move-CsCommonAreaPhone</strong> cmdlet 不会通过管道传递对象。</p></td>
</tr>
<tr class="even">
<td><p><em>ProxyPool</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>此参数仅用于 Lync Online。不应将其与 Lync Server 的本地实现结合使用。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

字符串。**Move-CsCommonAreaPhone** cmdlet 接受通过管道传递的字符串值，代表公用区域电话的标识。

## 返回类型

默认情况下，**Move-CsCommonAreaPhone** cmdlet 不会返回任何对象或值。但是，如果包含 PassThru 参数，则此 cmdlet 将返回 Microsoft.Rtc.Management.ADConnect.Schema.OCSADCommonAreaPhoneContact 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsCommonAreaPhone](get-cscommonareaphone.md)  
[New-CsCommonAreaPhone](new-cscommonareaphone.md)  
[Remove-CsCommonAreaPhone](remove-cscommonareaphone.md)  
[Set-CsCommonAreaPhone](set-cscommonareaphone.md)

