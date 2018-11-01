---
title: Lync Server 2013：DeRegisterType 表
TOCTitle: DeRegisterType 表
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398142(v=OCS.15)
ms:contentKeyID: 49311929
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 DeRegisterType 表

 

_**上一次修改主题：** 2015-03-09_

DeRegisterType 表是一个静态表，用于存储可能的用户注销类型（例如“客户端已启动”、“注册过期”或“客户端停止响应”）的列表。


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
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>允许的值：</p>
<ul>
<li><p>0 - 未知</p></li>
<li><p>1 - 客户端启动的取消注册</p></li>
<li><p>2 - 注册过期</p></li>
<li><p>3 – 客户端崩溃</p></li>
<li><p>4 - 用户属性已更改</p></li>
<li><p>5 – 首选注册器已更改</p></li>
<li><p>6 - 旧客户端处于生存模式</p></li>
</ul></td>
</tr>
</tbody>
</table>

