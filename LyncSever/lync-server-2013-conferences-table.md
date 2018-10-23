---
title: Lync Server 2013：Conferences 表
TOCTitle: Conferences 表
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412964(v=OCS.15)
ms:contentKeyID: 49314151
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Conferences 表

 

_**上一次修改主题：** 2015-03-09_

此表中的每条记录都包含一次会议的详细呼叫信息。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>键/索引</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主</p></td>
<td><p>CDR 代理捕获会议请求的时间。仅用作主键对会议实例进行唯一标识。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>用于标识会话的 ID 号。与 <strong>SessionIdTime</strong> 共同用来唯一标识会议实例。*</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>会议 URI。有关详细信息，请参阅 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p> </p></td>
<td><p>可用于定期会议；定期会议的每个实例都具有相同的 <strong>ConferenceUri</strong> ，但 <strong>ConfInstance</strong> 不同。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>会议结束时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>会议结束时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>用于标识在其中捕获会议的池的 ID 号。有关详细信息，请参阅 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 Pools 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>用于标识此会议的组织者 URI 的 ID 号。有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>包含会议属性的位掩码。可能的值为：</p>
<ul>
<li><p>0X01</p></li>
<li><p>Synthetic</p></li>
<li><p>Transaction</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Processed</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>监控服务所使用的内部字段。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
</tbody>
</table>


\* 对于大多数会话，SessionIdSeq 值都为 1。如果有两个会话几乎在同一时间开始，则其中一个会话的 SessionIdSeq 将为 1，另一个则为 2，依此类推。

