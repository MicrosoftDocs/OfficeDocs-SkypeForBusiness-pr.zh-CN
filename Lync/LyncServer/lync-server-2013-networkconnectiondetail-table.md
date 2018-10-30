---
title: NetworkConnectionDetail 表
TOCTitle: NetworkConnectionDetail 表
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205185(v=OCS.15)
ms:contentKeyID: 49313986
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# NetworkConnectionDetail 表

 

_**上一次修改主题：** 2015-03-09_

NetworkConnectionDetail 表可将网络连接类型映射到在体验质量数据库中的其他位置使用的网络连接标识符。此表是在 Microsoft Lync Server 2013 中引入的。


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
<td><p><strong>NetworkConnectionDetailKey</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td><p>网络连接类型的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkConnectionDetail</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>唯一</p></td>
<td><p>对应于 NetworkConnectionDetailKey 的网络连接类型。允许的值包括：</p>
<ol>
<li><p>0 -- 有线</p></li>
<li><p>1 -- WiFi</p></li>
<li><p>2 -- 以太网</p></li>
</ol></td>
</tr>
</tbody>
</table>

