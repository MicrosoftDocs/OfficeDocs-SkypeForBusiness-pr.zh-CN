---
title: Lync Server 2013：Tenants 表
TOCTitle: Tenants 表
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412950(v=OCS.15)
ms:contentKeyID: 49314153
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Tenants 表

 

_**上一次修改主题：** 2015-03-09_

Tenants 表是一个支持表，用于存储各个租户的列表。表中的每条记录分别表示一个租户。

> [!NOTE]  
> 在本地部署中，CDR 使用内置租户 ID 指示不同的身份验证类型，例如公共 IM 连接、联盟和匿名。



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
<td><p><strong>TenantId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识此租户 ID 的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>允许的值：</p>
<ul>
<li><p>00000000-0000-0000-0000-000000000000 – 企业</p></li>
<li><p>00000000-0000-0000-0000-000000000001 – 联盟</p></li>
<li><p>00000000-0000-0000-0000-000000000002 – 匿名</p></li>
<li><p>00000000-0000-0000-0000-000000000003 – 公共 IM 连接</p></li>
</ul></td>
</tr>
</tbody>
</table>

