---
title: Lync Server 2013 中的 ErrorCategory 表
TOCTitle: Lync Server 2013 中的 ErrorCategory 表
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204675(v=OCS.15)
ms:contentKeyID: 49312027
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 ErrorCategory 表

 

_**上一次修改主题：** 2015-03-09_

ErrorCategory 表包含每个 Microsoft Lync Server 2013 诊断分类的友好名称。默认情况下，Lync Server 2013 使用下列分类：

  - 0 -- 成功

  - 1 -- 预期失败

  - 2 – 意外失败

此表是在 Microsoft Lync Server 2013 中引入的。


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
<td><p><strong>CategoryId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td><p>分类的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>Name</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>分配给分类的值和友好名称。允许的值有：</p>
<ul>
<li><p>0 -- 成功</p></li>
<li><p>1 -- 预期失败</p></li>
<li><p>2 – 意外失败</p></li>
</ul></td>
</tr>
</tbody>
</table>

