---
title: Lock-CsClientPin
TOCTitle: Lock-CsClientPin
ms:assetid: 81a9895f-96e3-43c9-9dac-8129358e446a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398650(v=OCS.15)
ms:contentKeyID: 49313421
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lock-CsClientPin

 

_**上一次修改主题：** 2015-03-09_

使管理员可以阻止用户使用个人标识号 (PIN) 身份验证。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Lock-CsClientPin -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

在示例 1 中，使用 **Lock-CsClientPin** cmdlet 锁定属于用户 kenmyer@litwareinc.com 的 PIN。

    Lock-CsClientPin -Identity "kenmyer@litwareinc.com"

## 示例 2

示例 2 使用 **Lock-CsClientPin** cmdlet 锁定当前已为其分配 PIN 的所有用户的 PIN。这是通过使用 **Get-CsUser** cmdlet 返回已启用 Lync Server 的所有用户的集合来完成的。将此集合通过管道传递到 **Get-CsClientPinInfo** cmdlet，后者与 **Where-Object** cmdlet 结合使用以返回 IsPinSet 属性等于 True 的用户的集合。然后，将筛选出的集合通过管道传递到 **Lock-CsClientPin** cmdlet，后者可以锁定该集合中各个用户的 PIN。

    Get-CsUser | Get-CsClientPinInfo | Where-Object {$_.IsPinSet -eq $True} | Lock-CsClientPin

## 示例 3

在示例 3 中，使用 **Lock-CsClientPin** cmdlet 锁定其 PIN 已过期的所有用户的 PIN。为完成此任务，首先调用 **Get-CsUser** cmdlet 以返回已启用 Lync Server 的所有用户的集合。然后，将此集合通过管道传递到 **Get-CsClientPinInfo** cmdlet，后者与 **Where-Object** cmdlet 结合使用以将集合限制为仅包含 PIN 已过期的用户。为了确定哪些用户的 PIN 已过期，**Where-Object** cmdlet 会检查 PinExpirationTime 属性（指示 PIN 号的到期日期）早于当前日期的帐户。（使用 **Get-Date** cmdlet 检索当前日期。）如果到期日期（例如 2010 年 9 月 1 日）早于当前日期（例如 2010 年 9 月 2 日），则意味着此 PIN 已过期。然后，使用 **Lock-CsClientPin** cmdlet 锁定每个已过期的 PIN。

    Get-CsUser | Get-CsClientPinInfo | Where-Object {$_.PinExpirationTime -lt (Get-Date)} | Lock-CsClientPin

## 详细说明

通过 Lync Server，用户可以使用电话连接到系统或加入公用电话交换网 (PSTN) 会议。通常，登录到系统或加入会议会要求用户输入用户名或密码。但是，如果您使用的电话没有字母数字键盘，则输入用户名和密码可能会是一个问题。因此，您可以通过 Lync Server 为用户提供仅数字的 PIN；当系统提示时，用户可以通过输入 PIN 而不是用户名和密码来登录到系统或加入会议。

作为一种安全措施，Lync Server 使您可以锁定某个用户的 PIN。锁定某个 PIN 号后，该用户将无法再使用此 PIN 访问系统或加入会议。（但是，该用户仍可以通过使用诸如 Lync 2013 等应用程序，并提供用户名和密码来访问系统和加入会议。）锁定某个 PIN 后，恢复此 PIN（以及用户的访问权限）的唯一方法是由管理员解除此 PIN 的锁定。可以使用 **Unlock-CsClientPin** cmdlet 来执行此操作。

**Lock-CsClientPin** cmdlet 使管理员可以暂时禁止用户使用 PIN 身份验证访问系统。PIN 也可被系统锁定：如果用户多次登录系统失败，其 PIN 将自动锁定，此时也需要由管理员解除锁定。

请注意，默认情况下，在安装标准版本的 Lync Server 时，不会对 SQL Server Express 启用防火墙例外。这意味着您将无法从 Windows PowerShell 的远程实例运行 **Lock-CsClientPin** cmdlet；原因是您的命令无法穿越防火墙并访问 SQL Server Express 数据库。（但是，仍然可以在 Standard Edition Server 自身上本地运行该 cmdlet。）要远程运行 **Lock-CsClientPin** cmdlet，需要手动为 SQL Server Express 启用防火墙例外。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Lock-CsClientPin** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Lock-CsClientPin"}

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
<td><p>应锁定 PIN 的用户帐户的标识。可以采用下列四种格式之一来指定用户标识：1) 用户的 SIP 地址；2) 用户的用户主体名称 (UPN)；3) 用户的域名和登录名，格式为“域名\登录名”（如 litwareinc\kenmyer）；以及 4) 用户的 Active Directory 显示名称（例如 Ken Myer）。还可以使用用户的 Active Directory 可分辨名称来引用用户标识。</p>
<p>此外，在使用显示名称作为用户标识时，还可以使用通配符星号 (*)。例如，标识“* Smith”将返回显示名称以字符串值“Smith”结尾的所有用户。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

字符串值或 Microsoft.Rtc.Management.ADConnect.Schema.ADUser 对象。**Lock-CsClientPin** cmdlet 接受通过管道传递的代表用户帐户 Identity 的字符串值的输入。该 cmdlet 还接受通过管道传递的用户对象的输入。

## 返回类型

**Lock-CsClientPin** cmdlet 不会返回值或对象。此 cmdlet 会配置 Microsoft.Rtc.Management.UserPinService.PinInfoDetails 对象的一个或多个实例。

## 另请参阅

#### 其他资源

[Get-CsClientPinInfo](get-csclientpininfo.md)  
[Set-CsClientPin](set-csclientpin.md)  
[Unlock-CsClientPin](unlock-csclientpin.md)

