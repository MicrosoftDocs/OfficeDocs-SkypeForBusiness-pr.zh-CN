---
title: VoIPDetails 视图
TOCTitle: VoIPDetails 视图
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49888308
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VoIPDetails 视图

 

_**上一次修改主题：** 2015-03-09_

VoIPDetails 视图存储有关对等会话（其中至少有一个用户是 VoIP 用户）的信息。此视图是在 Microsoft Lync Server 2013 中引入的。

> [!NOTE]  
> 除了下面列出的列之外，VoIPDetails 视图还包含 <a href="lync-server-2013-sessiondetails-view.md">SessionDetails 视图</a>中的所有列。



<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FromPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>启动会话的用户的电话 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>加入会话的用户的电话 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>断开会话的用户的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>断开会话的用户的 URI 的类型。有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>断开会话的用户的租户。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>断开会话的用户的电话 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>启动会话的用户使用的中介服务器。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>加入会话的用户使用的中介服务器。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>启动会话的用户使用的网关。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>加入会话的用户使用的网关。</p></td>
</tr>
</tbody>
</table>

