---
title: Lync Server 2013：EndpointSubnet 表
TOCTitle: EndpointSubnet 表
ms:assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398933(v=OCS.15)
ms:contentKeyID: 49314385
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 EndpointSubnet 表

 

_**上一次修改主题：** 2015-03-09_

EndpointSubnet 表是一个支持表。每个记录代表从终结点捕获的一个子网。


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
<td><p><strong>SubnetIP</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>子网的整数表示形式。</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
</tbody>
</table>

