---
title: 管理策略
TOCTitle: 管理策略
ms:assetid: 91372888-a96e-44db-a0dc-d08facbfce87
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362826(v=OCS.15)
ms:contentKeyID: 56271178
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理策略

 

_**上一次修改主题：** 2015-06-22_

以下 cmdlet 管理 Skype for Business Online 策略。策略可帮助确定用户和整个组织可以使用的 Skype for Business Online 功能。


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
<td><p><a href="get-csclientpolicy.md">Get-CsClientPolicy</a><br />
<a href="grant-csclientpolicy.md">Grant-CsClientPolicy</a></p></td>
<td><p>客户端策略用于确定用户可以使用的 Lync 客户端功能。例如，您可以向一些用户提供传输文件的功能，而不向其他用户提供该功能。</p></td>
</tr>
<tr class="even">
<td><p><a href="get-csconferencingpolicy.md">Get-CsConferencingPolicy</a><br />
<a href="grant-csconferencingpolicy.md">Grant-CsConferencingPolicy</a></p></td>
<td><p>会议策略可确定会议中可以使用的各种功能，从会议能否包括 IP 音频和视频，到能够参加会议的最大人数等全部内容都包含在内。</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-csexternalaccesspolicy.md">Get-CsExternalAccessPolicy</a><br />
<a href="grant-csexternalaccesspolicy.md">Grant-CsExternalAccessPolicy</a></p></td>
<td><p>外部访问策略用于确定是否允许您的用户与来自联盟域的用户进行通信以及/或者是否允许您的用户与在公共 IM 提供商（如 Windows Live 或 AOL）上拥有帐户的用户进行通信。</p></td>
</tr>
<tr class="even">
<td><p><a href="get-csvoicepolicy.md">Get-CsVoicePolicy</a><br />
<a href="grant-csvoicepolicy.md">Grant-CsVoicePolicy</a><br />
<a href="remove-csvoicepolicy.md">Remove-CsVoicePolicy</a></p></td>
<td><p>语音策略用于管理企业语音功能，例如同时拨打（每次有人拨打办公电话时可以同时使第二部电话响铃的功能）和呼叫转接。</p></td>
</tr>
</tbody>
</table>


您也可以使用 Skype for Business Online 管理中心管理选择的会议策略设置：

![Lync 管理中心 - 常规选项属性](images/Dn362826.acf90793-7ee4-4faf-b791-f149dd5df2a5(OCS.15).png "Lync 管理中心 - 常规选项属性")

您也可以使用 Skype for Business Online 管理中心管理外部访问策略设置。

![管理中心 - 外部通信选项](images/Dn362826.e5cfb159-b096-463e-b1ef-2b42eb29168a(OCS.15).png "管理中心 - 外部通信选项")

## 另请参阅

#### 概念

[Lync Online Cmdlet](the-skype-for-business-online-cmdlets.md)  
[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

