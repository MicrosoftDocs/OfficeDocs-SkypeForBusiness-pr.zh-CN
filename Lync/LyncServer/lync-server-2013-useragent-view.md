---
title: UserAgent 视图
TOCTitle: UserAgent 视图
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49888582
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# UserAgent 视图

 

_**上一次修改主题：** 2015-03-09_

UserAgent 视图会存储有关在数据库中含有记录的会话中所涉及的用户代理的信息。此视图是在 Microsoft Lync Server 2013 中引入的。


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
<td><p>UserAgentKey</p></td>
<td><p>int</p></td>
<td><p>标识此用户代理的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p>UserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>用户代理字符串。</p></td>
</tr>
<tr class="odd">
<td><p>UAType</p></td>
<td><p>smallint</p></td>
<td><p>用户代理的类型。有关详细信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>UACategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>用户代理所属的类别。例如，用户代理 Conferencing_Attendant_1.0 属于 UACategory CAA。</p></td>
</tr>
</tbody>
</table>

