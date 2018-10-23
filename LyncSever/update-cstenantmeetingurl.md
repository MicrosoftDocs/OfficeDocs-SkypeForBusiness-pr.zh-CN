---
title: Update-CsTenantMeetingUrl
TOCTitle: Update-CsTenantMeetingUrl
ms:assetid: 9aed3ede-bbd3-405a-997f-f7553e66aecd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn424754(v=OCS.15)
ms:contentKeyID: 59602820
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Update-CsTenantMeetingUrl

 

_**上一次修改主题：** 2015-03-09_

更新指定 Skype for Business Online 租户的会议 URL。更新的 URL 使用更简单、更标准化的格式，便于客户端查找和连接到会议。

此 cmdlet 仅适用于与 Skype for Business Online 结合使用。

## 语法

    Update-CsTenantMeetingUrl [-Tenant] <guid> [-Force] [-WhatIf] [-Confirm]

## 示例

## 示例 1

示例 1 中显示的命令更新租户 ID 为 38aad667-af54-4397-aaa7-e94c79ec2308 的租户的会议 URL。（请注意，您必须提供租户 ID，此命令才能完成。）按 Enter 以运行命令后，系统将询问您是否确定要更新会议 URL。您必须对此提示回答“是”，Update-CsTenantMeetingUrl 才会实际对您的 Skype for Business Online 配置设置做更改。

    Update-CsTenantMeetingUrl -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308"

## 示例 2

示例 2 也更新租户 ID 为 38aad667-af54-4397-aaa7-e94c79ec2308 的租户的会议 URL。但是在此示例中，包括 Force 参数；这将绕过当您运行 Update-CsTenantMeetingUrl 时通常出现的确定提示。在这种情况下，一旦您按 Enter，命令就将运行，您的 Skype for Business Online 配置设置将被修改。

    Update-CsTenantMeetingUrl -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -Force

## 详细说明

Update-CsTenantMeetingUrl 会将 Skype for Business Online 会议 URL 更新为更简单、更标准化的格式；这可帮助避免原始会议 URL 有时会发生的问题。例如，假设组织设置名为 contoso.onmicrosoft.com 的 Office 365 域。当他们执行该操作时，会议将具有如下所示的 URL：

https://meet.lync.com/onmicrosoft/contoso/user1/45GZFH99

现在，假设组织经历一些变化，决定使用“虚”URL litwareinc.com，而不使用 onmicrosoft.com URL。组织修改了其电子邮件地址以使用 litwareinc.com 域。但是，会议 URL 仍使用旧域名：

https://meet.lync.com/contoso/user1/45GZFH99

要解决此问题，管理员应运行 Update-CsTenantMeetingUrl cmdlet。这样做会将旧会议 URL 替换为具备虚 URL 的新会议 URL：

https://meet.lync.com/litwareinc.com/user1/37JYLP71

运行 Update-CsTenantMeetingUrl cmdlet 是做此更改的唯一方法。

请注意，当您运行 Update-CsTenantMeetingUrl 时，您的 Skype for Business Online 租户在较短同步延迟后将立即切换到新 URL。这不会给您的用户可能安排的新会议带来任何问题：那些会议将自动使用新 URL 进行安排。但是，以前安排的会议将遇到问题；这是因为它们是使用较旧、不起作用的会议 URL 安排的。解决此问题的唯一方法是让您的用户重新安排这些会议。

由于这在一些组织（特别是已经安排了大量会议的组织）可能会引起问题，默认情况下，Update-CsTenantMeetingUrl 将在实际更新会议 URL 之前提示您：

警告：这是面向此租户中的用户的最新更改。会议 URL 配置将更新！旧会议 URL 不再起作用。此更新不可恢复。  
是否确实要继续？  
\[Y\] 是 \[A\] 全是 \[N\] 否 \[L\] 全否 \[S\] 挂起 \[?\] 帮助 (默认值为“Y”):

在命令实际执行之前，您必须回答“是”或“全是”；如果回答“否”，则命令将被取消，会议 URL 不会更新。记住，一旦会议 URL 已更新，无法再恢复为原始 URL。一旦命令执行，URL 将会更改，所有以前安排的会议需要重新安排。这也意味着您需要对每个租户运行此命令一次。不需要定期运行该命令和重新更新会议 URL。

如果您更喜欢运行命令时不必应答确认提示，则可以包括 Force 参数。在这种情况下，Update-CsTenantMeetingUrl 运行时不显示确认提示：

警告：这是面向此租户中的用户的最新更改。会议 URL 配置将更新！

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
<td><p><strong>Tenant</strong></p></td>
<td><p>必需</p></td>
<td><p>System.Guid</p></td>
<td><p>返回其联盟设置的租户帐户的全局唯一标识符 (GUID)。例如：</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>可以通过运行以下命令来返回每个租户的租户 ID：</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>如果不包括 Tenant 参数，Update-CsMeetingUrl 将在您可以继续之前提示您输入该参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p>
<p>请注意，Update-CsMeetingUrl 的默认行为是在做任何更改之前显示确认提示。这意味着，如果您想要显示确认提示，则不需要包括 Confirm 参数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Force</strong></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示 Update-CsMeetingUrl 做任何更新之前出现的确认提示。</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述如果执行命令会发生什么情况（无需实际执行命令）。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。Update-CsMeetingUrl 不接受通过管道传递的输入。

## 返回类型

无。

## 另请参阅

#### 其他资源

[Get-CsSimpleUrlConfiguration](get-cssimpleurlconfiguration.md)

