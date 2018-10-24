---
title: 在 Lync Server 2013 中会议策略设置参考
TOCTitle: 在 Lync Server 2013 中会议策略设置参考
ms:assetid: ec8125f7-ef78-4a2b-8db0-4dd3cf5a4065
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429724(v=OCS.15)
ms:contentKeyID: 49314646
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中会议策略设置参考

 

_**上一次修改主题：** 2014-04-22_

本主题中的表格列出了可以使用 Lync Server 2013 控制面板指定的所有会议策略设置。

## 组织者策略设置

下表列出了可应用于会议组织者的所有会议策略设置。有关最新的会议策略设置列表，请参阅 [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy) cmdlet 的帮助主题。

### 组织者策略设置

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>设置</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>最大会议规模</p></td>
<td><p>设置会议中允许的最大参与者人数。</p></td>
</tr>
<tr class="even">
<td><p>允许参与者邀请匿名用户</p></td>
<td><p>允许会议组织者邀请未经身份验证的用户参加会议。</p></td>
</tr>
<tr class="odd">
<td><p>启用录制</p></td>
<td><p>允许演示者或与会者录制会议。</p></td>
</tr>
<tr class="even">
<td><p>允许联盟参与者和匿名参与者录制</p></td>
<td><p>允许外部参与者和未经身份验证的参与者录制会议。</p></td>
</tr>
<tr class="odd">
<td><p>启用 IP 音频</p></td>
<td><p>允许在会议中使用音频。</p></td>
</tr>
<tr class="even">
<td><p>启用 IP 音频/视频</p></td>
<td><p>允许在会议中使用音频和视频。</p></td>
</tr>
<tr class="odd">
<td><p>启用 PSTN 电话拨入式会议</p></td>
<td><p>允许用户通过公用电话交换网 (PSTN) 拨号加入会议。</p></td>
</tr>
<tr class="even">
<td><p>允许匿名参与者拨出</p></td>
<td><p>允许未经身份验证的用户使用拨出式电话加入会议。通过拨出式电话，会议服务器会呼叫用户，用户接听电话即可加入会议。</p></td>
</tr>
<tr class="odd">
<td><p>允许的会议最大视频分辨率</p></td>
<td><p>设置视频会议的最大分辨率。有效值为“640*480(VGA)”和“352*288(CIF)”。</p></td>
</tr>
<tr class="even">
<td><p>启用数据协作</p></td>
<td><p>启用数据协作会议或 Web 会议。</p></td>
</tr>
<tr class="odd">
<td><p>允许联盟参与者和匿名参与者下载内容</p></td>
<td><p>允许外部参与者和未经身份验证的参与者下载会议内容。</p></td>
</tr>
<tr class="even">
<td><p>允许参与者传输文件</p></td>
<td><p>允许会议参与者在会议期间传输文件。</p></td>
</tr>
<tr class="odd">
<td><p>启用批注</p></td>
<td><p>允许会议参与者在内容中创建批注。</p></td>
</tr>
<tr class="even">
<td><p>启用投票</p></td>
<td><p>允许会议参与者在会议期间举行投票。</p></td>
</tr>
<tr class="odd">
<td><p>启用应用程序共享</p></td>
<td><p>允许用户安排支持应用程序共享的会议。</p></td>
</tr>
<tr class="even">
<td><p>允许参与者获得控制权</p></td>
<td><p>允许参与者获得另一个用户的共享应用程序的控制权。</p></td>
</tr>
<tr class="odd">
<td><p>允许联盟参与者和匿名参与者获得控制权</p></td>
<td><p>允许外部参与者和匿名参与者获得另一个用户的共享应用程序的控制权。</p>
<div>

> [!NOTE]  
> 如果此设置设为 True，而“允许参与者获得控制权”设为 False，则此设置将被覆盖。


</div></td>
</tr>
</tbody>
</table>


## 参与者策略设置

下表列出了可应用于会议参与者的所有会议策略设置。

### 参与者策略设置

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>设置</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>启用应用程序共享</p></td>
<td><p>允许用户安排支持应用程序共享的会议。</p></td>
</tr>
<tr class="even">
<td><p>启用应用程序和桌面共享</p></td>
<td><p>允许用户参与支持应用程序共享和桌面共享的会议。在会议中，适用于会议组织者的此设置的值将适用于也参加的所有匿名终结点。</p></td>
</tr>
<tr class="odd">
<td><p>启用对等文件传输</p></td>
<td><p>允许参与者在会议期间执行对等文件传输。对等文件传输不涉及全部会议参与者。</p></td>
</tr>
<tr class="even">
<td><p>启用对等录制</p></td>
<td><p>允许参与者录制对等会议会话。</p></td>
</tr>
</tbody>
</table>

