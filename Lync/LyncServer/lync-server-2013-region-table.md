---
title: Lync Server 2013：Region 表
TOCTitle: Region 表
ms:assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398235(v=OCS.15)
ms:contentKeyID: 49312120
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Region 表

 

_**上一次修改主题：** 2015-03-09_

区域表是一个支持表。每条记录代表网络配置设置中定义的一个国家/区域。


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
<td><p><strong>RegionKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识国家/区域的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>RegionName</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>唯一</p></td>
<td><p>国家/区域的名称。</p></td>
</tr>
</tbody>
</table>

