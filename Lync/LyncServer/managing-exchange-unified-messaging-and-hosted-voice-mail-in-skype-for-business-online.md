---
title: 管理 Exchange 统一消息和托管语音邮件
TOCTitle: 管理 Exchange 统一消息和托管语音邮件
ms:assetid: 844bf8d5-e093-4dcd-abcf-48dc70e8c73c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362822(v=OCS.15)
ms:contentKeyID: 56271173
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理 Exchange 统一消息和托管语音邮件

 

_**上一次修改主题：** 2015-06-22_

以下 cmdlet 可用于管理 Exchange 统一消息 (UM) 和托管语音邮件策略：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="get-csexumcontact.md">Get-CsExUmContact</a></p>
<p><a href="new-csexumcontact.md">New-CsExUmContact</a></p>
<p><a href="remove-csexumcontact.md">Remove-CsExUmContact</a></p>
<p><a href="set-csexumcontact.md">Set-CsExUmContact</a></p></td>
<td><p>创建和管理当 Exchange UM 是托管服务时用于自动助理和订阅者访问服务的联系人对象。</p>
<p>Skype for Business Online 与 Exchange UM 结合使用可提供一些与语音相关的功能，包括自动助理和订阅者访问。自动助理提供一种方法自动应答呼叫和将呼叫路由给正确的人员。订阅者访问使用户能够连接到 Exchange UM 并检索电子邮件、语音消息、联系人和日历信息。</p>
<p>当 Exchange UM 以托管服务的形式提供时，必须使用 Windows PowerShell 创建用于自动助理和订阅者访问服务的联系人对象。这些对象是使用 CsExUmContact cmdlet 创建并管理的。</p></td>
</tr>
<tr class="even">
<td><p><a href="get-cshostedvoicemailpolicy.md">Get-CsHostedVoicemailPolicy</a></p>
<p><a href="grant-cshostedvoicemailpolicy.md">Grant-CsHostedVoicemailPolicy</a></p></td>
<td><p>管理组织中使用的托管语音邮件策略。托管语音邮件策略指定未应答呼叫如何路由到 Exchange UM 服务。这些策略仅影响启用了 Exchange UM 托管语音邮件的用户。要验证用户是否已启用托管语音邮件，请从 Windows PowerShell 提示符处运行与此类似的命令：</p>
<pre><code>Get-CsOnlineUser -Identity &quot;kenmyer@litwareinc.com&quot; | Select-Object HostedVoiceMail</code></pre></td>
</tr>
</tbody>
</table>


您不能使用 Skype for Business Online 管理中心管理 Exchange UM 设置和托管语音邮件策略。

## 另请参阅

#### 概念

[Lync Online Cmdlet](the-skype-for-business-online-cmdlets.md)  
[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

