---
title: Lync Server 2013：User 表
TOCTitle: User 表
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398505(v=OCS.15)
ms:contentKeyID: 49313161
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 User 表

 

_**上一次修改主题：** 2015-03-09_

User 表是一个支持表，用于存储已参与数据库中记录的会话的各种用户的列表。该表中的每条记录表示一个用户。


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
<td><p><strong>UserKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>用于标识此用户的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>URI</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>唯一</p></td>
<td><p>URI 字符串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>URIType</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>1 是未知 URI 类型。</p>
<p>2 是用户 URI。</p>
<p>4 是会议 URI。</p>
<p>8 是电话 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>用户的租户，被 Tenant 表引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastPoorCallTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>用户具有较差音频呼叫时的最新时间戳。</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
</tbody>
</table>

