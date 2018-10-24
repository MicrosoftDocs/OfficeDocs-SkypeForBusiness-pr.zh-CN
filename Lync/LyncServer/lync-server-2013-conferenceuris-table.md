---
title: Lync Server 2013：ConferenceUris 表
TOCTitle: ConferenceUris 表
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412854(v=OCS.15)
ms:contentKeyID: 49313978
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 ConferenceUris 表

 

_**上一次修改主题：** 2015-03-09_

ConfereneUris 表是一个支持表，用于存储已参与数据库中记录的会议会话的各种会议 URI 列表。表中的每条记录代表一个会议 URI。


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p>主</p></td>
<td><p>内部使用的时间戳。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识此会议 URI 的唯一编号。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p></p></td>
<td><p>会议 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>Checksum</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>ConferenceUri 的校验和。用于增加数据库搜索的速度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>URI 类型，如 conf:chat 代表 IM 会议，conf:audio-video 代表音频/视频会议。有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>表。</p></td>
</tr>
</tbody>
</table>

