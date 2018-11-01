---
title: Lync Server 2013：UriTypes 表
TOCTitle: UriTypes 表
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398587(v=OCS.15)
ms:contentKeyID: 49313306
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 UriTypes 表

 

_**上一次修改主题：** 2015-06-16_

UriTypes 表包含 Microsoft Lync Server 2013 中监控的不同的 URI（统一资源标识符）类型。


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
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td><p>分配给 URI 类型的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>UriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>不同的 URI 类型的描述。允许的值包括：</p>
<ul>
<li><p>0 – Phone Uri</p></li>
<li><p>1 – User Uri</p></li>
</ul></td>
</tr>
</tbody>
</table>

