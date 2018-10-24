---
title: Lync Server 2013：持久聊天服务器合规性表的列表
TOCTitle: 持久聊天服务器合规性表的列表
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ215878(v=OCS.15)
ms:contentKeyID: 49313468
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中持久聊天服务器合规性表的列表

 

_**上一次修改主题：** 2015-03-09_

持久聊天合规性数据库架构由以下表组成。

## 持久聊天服务器合规性表的列表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 中的 tblComplianceData</a></p></td>
<td><p>包含已配置的适配器尚未处理的合规性事件。</p>
<p>该表包含 持久聊天相关事件，例如聊天消息和文件下载。（参与者事件通过 tblComplianceParticipant 表进行跟踪。）</p>
<p>（处理该表中的事件的服务器列在 tblComplianceFanout 表中。）</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 中的 tblComplianceFanout</a></p></td>
<td><p>包含处理合规性事件的服务器。该表与 tblComplianceData 表联系紧密。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 中的 tblComplianceParticipant</a></p></td>
<td><p>包含每个聊天服务和每台服务器的当前参与者。该表根据通过 持久聊天服务接收的加入和离开合规性事件进行维护。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 中的 tblComplianceState</a></p></td>
<td><p>包含池范围的合规性状态信息。</p></td>
</tr>
</tbody>
</table>

