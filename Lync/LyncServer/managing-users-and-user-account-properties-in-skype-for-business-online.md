---
title: 管理用户和用户帐户属性
TOCTitle: 管理用户和用户帐户属性
ms:assetid: 5d13ab15-0e12-4bd0-a970-f130de980404
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362790(v=OCS.15)
ms:contentKeyID: 56271147
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理用户和用户帐户属性

 

_**上一次修改主题：** 2015-06-22_

以下 cmdlet 管理 Skype for Business Online 用户帐户。


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
<td><p><a href="get-csonlineuser.md">Get-CsOnlineUser</a></p></td>
<td><p>返回有关其帐户使用 Skype for Business Online 租户托管的用户的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="get-csuseracp.md">Get-CsUserAcp</a><br />
<a href="remove-csuseracp.md">Remove-CsUserAcp</a><br />
<a href="set-csuseracp.md">Set-CsUserAcp</a></p></td>
<td><p>使您能够向单个用户分配、修改或取消分配音频会议提供商。</p>
<p>音频会议提供商是一个第三方公司，它向组织提供会议服务，包括最高端服务，如实时翻译、转录和每个会议的实时接线员协助。</p>
<p>这些 cmdlet 不会返回有关可分配给这些用户的音频提供商的信息。对于该信息，请运行此命令：</p>
<pre><code>Get-CsAudioConferencingProvider</code></pre></td>
</tr>
</tbody>
</table>


> [!WARNING]  
> Set-CsUser cmdlet 也包括在可供 Skype for Business Online 管理员使用的一组 cmdlet 中。但是，Set-CsUser 当前不能用于管理 Skype for Business Online，设置 AudioVideoDisabled 参数除外。如果您试图运行该 cmdlet 和任何其他参数，命令将会失败，并出现以下类似错误消息：<br />
> 无法设置“SipAddress”。此参数在远程租户 PowerShell 中受限制。


音频会议提供商也可使用 Skype for Business Online 管理中心分配给用户帐户或从用户帐户取消分配：

![Lync 管理中心 - 电话拨入式会议属性](images/Dn362790.0c61f0c2-8aef-4020-a0a8-02580d43092a(OCS.15).png "Lync 管理中心 - 电话拨入式会议属性")

## 另请参阅

#### 概念

[Lync Online Cmdlet](the-skype-for-business-online-cmdlets.md)  
[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

