---
title: Lync Server 2013：MediationServers 表
TOCTitle: MediationServers 表
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412743(v=OCS.15)
ms:contentKeyID: 49313769
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 MediationServers 表

 

_**上一次修改主题：** 2015-03-09_

MediationServers 表是一个支持表。每条记录都存储有关在数据库中具有记录的呼叫中所涉及的一台中介服务器的信息。


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
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识此中介服务器的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>中介服务器名称。</p></td>
</tr>
</tbody>
</table>

