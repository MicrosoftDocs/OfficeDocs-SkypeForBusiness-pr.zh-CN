---
title: Lync Server 2013 中的 SIPResponseMetaData 表
TOCTitle: Lync Server 2013 中的 SIPResponseMetaData 表
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205294(v=OCS.15)
ms:contentKeyID: 49314298
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 SIPResponseMetaData 表

 

_**上一次修改主题：** 2015-03-09_

SIPResponseMetaDataTable 包含 SIP 响应代码的列表以及每种代码的分类和定义。在响应影响 SIP 设备和 SIP 通信会话的事件时生成这些代码；例如，当某个 SIP 设备发出请求，但服务器拒绝服从该请求时，将生成响应代码 403。

该表在 Microsoft Lync Server 2013 中引入。


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
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>表示 SIP 响应代码的数字值。</p></td>
</tr>
<tr class="even">
<td><p><strong>Class</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>响应代码的常规分类。分类包括：</p>
<ul>
<li><p>1 – 信息响应</p></li>
<li><p>2 – 成功响应</p></li>
<li><p>3 – 重定向响应</p></li>
<li><p>4 – 客户端失败响应</p></li>
<li><p>5 – 服务器失败响应</p></li>
<li><p>6 – 全局失败响应</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>SIP 响应代码的说明。例如，响应代码 181 的说明如下：</p>
<p>Call Is Being Forwarded</p></td>
</tr>
</tbody>
</table>

