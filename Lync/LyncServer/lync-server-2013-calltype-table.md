---
title: Lync Server 2013：CallType 表
TOCTitle: CallType 表
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412752(v=OCS.15)
ms:contentKeyID: 49313790
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 CallType 表

 

_**上一次修改主题：** 2015-03-09_

CallType 表是存储可能的呼叫类型列表的静态表。


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
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar</p></td>
<td><p></p></td>
<td><p>允许的值：</p>
<ul>
<li><p>0 – 未知</p></li>
<li><p>1 - 即时消息</p></li>
<li><p>2 – 应用程序共享</p></li>
<li><p>3 – 音频</p></li>
<li><p>4 - 音频和视频</p></li>
<li><p>5 - 文件传输</p></li>
</ul></td>
</tr>
</tbody>
</table>

