---
title: Lync Server 2013 中的 UserStatistics 表
TOCTitle: Lync Server 2013 中的 UserStatistics 表
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49888621
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 UserStatistics 表

 

_**上一次修改主题：** 2015-03-09_

UserStatistics 表是一个支持表。该表中的每条记录都存储了单个用户的系统使用情况的信息。该表在 Microsoft Lync Server 2013 中引入。


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
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>用于标识此用户的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>LastLogInTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>用户上次登录时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizedTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>用户上次组织会议的时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>LastCallOrganizerCallFailureTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>用户上次遇到呼叫失败的时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizerCallFailureTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>用户上次以会议组织者身份遇到呼叫失败的时间。</p></td>
</tr>
</tbody>
</table>

