---
title: Lync Server 2013：MacAddress 表
TOCTitle: MacAddress 表
ms:assetid: a32e68c5-3f95-4217-aff4-cb3d1cc70505
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412761(v=OCS.15)
ms:contentKeyID: 49313798
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 MacAddress 表

 

_**上一次修改主题：** 2015-03-09_

MacAddress 表是一个支持表。每条记录分别表示一个来源。


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
<td><p><strong>MacAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识 Mac 地址的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>唯一</p></td>
<td><p>Mac 地址字符串。</p></td>
</tr>
</tbody>
</table>

