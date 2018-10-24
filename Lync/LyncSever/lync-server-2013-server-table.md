---
title: Lync Server 2013：Server 表
TOCTitle: Server 表
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398801(v=OCS.15)
ms:contentKeyID: 49313704
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Server 表

 

_**上一次修改主题：** 2015-03-09_

Server 表是一个支持表。每个记录表示一台服务器。


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
<td><p><strong>ServerKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识服务器的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDNOrIP</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>索引</p></td>
<td><p>MAC 地址字符串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerType</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>1：中介服务器</p>
<p>2：A/V 会议服务器 16394：A/V 边缘服务 32769：网关</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar (512)</p></td>
<td><p></p></td>
<td><p>服务器所属的池。仅适用于 A/V 会议服务器。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
</tbody>
</table>

