---
title: Lync Server 2013：Mcus 表
TOCTitle: Mcus 表
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425742(v=OCS.15)
ms:contentKeyID: 49312300
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Mcus 表

 

_**上一次修改主题：** 2015-03-09_

Mcus 表是一个支持表。每条记录存储有关一个会议服务的信息。这些服务可以包括 IM 会议服务和电话会议服务（作为前端服务器上的进程运行）以及 Web 会议服务和 A/V 会议服务。


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
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>用于标识此会议服务器的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><strong>McuTypeId</strong></p></td>
<td><p>inyint</p></td>
<td><p>外</p></td>
<td><p>会议服务器类型，例如 conf:chat（对于 IM）或 conf:audio-video。有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
</tbody>
</table>

