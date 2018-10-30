---
title: Lync Server 2013：MediaList 表
TOCTitle: MediaList 表
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398279(v=OCS.15)
ms:contentKeyID: 49312209
ms.date: 07/12/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 MediaList 表

 

_**上一次修改主题：** 2016-07-12_

MediaList 表是一个静态表，用于存储各种媒体类型的列表。


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
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>允许的值：</p>
<ul>
<li><p>1 – IM</p></li>
<li><p>2 – 文件传输</p></li>
<li><p>3 – 远程协助</p></li>
<li><p>4 – 应用程序共享</p></li>
<li><p>5 – 音频</p></li>
<li><p>6 – 视频</p></li>
<li><p>7 – 应用程序邀请</p></li>
</ul></td>
</tr>
</tbody>
</table>

