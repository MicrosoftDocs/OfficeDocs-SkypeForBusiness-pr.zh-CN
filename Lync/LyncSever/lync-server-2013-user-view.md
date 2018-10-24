---
title: 用户视图
TOCTitle: 用户视图
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49888472
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用户视图

 

_**上一次修改主题：** 2015-03-09_

用户视图存储有关数据库中记录的呼叫或会话所涉及的用户的信息。此视图是在 Microsoft Lync Server 2013 中引入的。


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
<td><p>UserId</p></td>
<td><p>int</p></td>
<td><p>用于标识此用户的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p>UserUri</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>用户的 URI。</p></td>
</tr>
<tr class="odd">
<td><p>TenantKey</p></td>
<td><p>uniqueidentifier</p></td>
<td><p>用户的租户。有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的 Tenants 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>UriType</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>用户 URI 的类型。有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
</tbody>
</table>

