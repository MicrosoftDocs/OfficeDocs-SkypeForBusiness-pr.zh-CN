---
title: Lync Server 2013：UserAgent 表
TOCTitle: UserAgent 表
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398939(v=OCS.15)
ms:contentKeyID: 49314391
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 UserAgent 表

 

_**上一次修改主题：** 2015-03-09_

UserAgent 表是一个支持表，用于存储已参与数据库中所记录会话的各种用户代理的列表。表中的每个记录代表一个用户代理


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>数据类型</strong></th>
<th><strong>键/索引</strong></th>
<th><strong>详细信息</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserAgentKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识此用户代理的唯一数字。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>唯一</p></td>
<td><p>用户代理字符串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1 是中介服务器。</p>
<p>2 是 A/V 会议服务器。</p>
<p>4 是 Lync。</p>
<p>8 是 IP 电话。</p>
<p>16 是 Live Meeting 控制台。</p>
<p>32 是部署验证工具 (DVT)。</p>
<p>64 是 Macintosh 计算机上的 Lync。</p>
<p>128 是 Office Communications Server 2007 R2 Attendant。</p>
<p>256 是会议公告服务。</p>
<p>512 是会议自动助理。</p>
<p>1024 是响应组应用程序。</p>
<p>2048 是外部语音控制。</p></td>
</tr>
</tbody>
</table>

