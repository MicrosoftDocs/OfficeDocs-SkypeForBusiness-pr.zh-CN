---
title: 管理 Lync 客户端
TOCTitle: 管理 Lync 客户端
ms:assetid: d1ccc7b6-99ff-4ffd-bd29-9088fb8fe837
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362847(v=OCS.15)
ms:contentKeyID: 56271207
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理 Lync 客户端

 

_**上一次修改主题：** 2015-06-22_

以下 cmdlet 管理 Lync 客户端：


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
<td><p><a href="get-csimfilterconfiguration.md">Get-CsImFilterConfiguration</a></p></td>
<td><p>检索有关您的组织中正在使用的 URI 限制的信息。</p>
<p>发送即时消息时，用户可以在该消息文本中嵌入 URI，以便将对话中的其他参与者指引到特定网站或共享。可以将 Skype for Business Online 配置为阻止包含某些前缀的超链接，或者使这类超链接处于非活动状态。这帮助确保参与者无法单击链接并转到 URI 指向的网站。相反，他们必须手动复制链接并将其粘贴到浏览器中。</p></td>
</tr>
<tr class="even">
<td><p><a href="get-cspresencepolicy.md">Get-CsPresencePolicy</a></p></td>
<td><p>返回有关状态订阅的两个重要方面的信息：提示订阅者和类别订阅。</p>
<p>在将您添加到某人的联系人列表时，默认情况下，您会收到一条弹出式通知，告知您已被添加到该列表中。在消除弹出式通知之前，每条通知都将视为一个提示订阅者。</p>
<p>类别订阅表示对特定类别信息的请求，例如，请求日历数据的应用程序。</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-csprivacyconfiguration.md">Get-CsPrivacyConfiguration</a><br />
<a href="set-csprivacyconfiguration.md">Set-CsPrivacyConfiguration</a></p></td>
<td><p>在 Skype for Business Online 中配置默认隐私值，同时仍允许用户选择更改这些值。</p>
<p>通过 Skype for Business Online，用户可以与其他人共享大量的状态信息。用户可以发布自己的照片，提供详细的位置信息，并向组织中的所有人自动提供状态信息（而不是仅向用户联系人列表上的人员提供此信息）。<strong>CsPrivacyConfiguration</strong> cmdlet 使管理员能够在 Skype for Business Online 中配置默认隐私值，同时仍允许用户选择更改这些值。</p></td>
</tr>
</tbody>
</table>


您也可以使用 Skype for Business Online 管理中心管理一小部分隐私配置设置：

![Lync 管理中心 - 状态专用模式设置](images/Dn362847.eb206b74-844d-4a7b-b1b3-0cfcb6e3614b(OCS.15).png "Lync 管理中心 - 状态专用模式设置")

## 另请参阅

#### 概念

[Lync Online Cmdlet](the-skype-for-business-online-cmdlets.md)  
[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

