---
title: Lync Server 2013 中的 CodecDescription 表
TOCTitle: Lync Server 2013 中的 CodecDescription 表
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204797(v=OCS.15)
ms:contentKeyID: 49312471
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 CodecDescription 表

 

_**上一次修改主题：** 2015-03-09_

CodecDescription 表可将唯一编解码器标识符映射到其相应的编解码器。编解码器用于对传输和广播的数字信号进行编码，然后解码这些信号以进行播放。此表是在 Microsoft Lync Server 2013 中引入的


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
<td><p><strong>CodecDescriptionKey</strong></p></td>
<td><p>smallint</p></td>
<td><p>主</p></td>
<td><p>分配给编解码器的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>CodecDescription</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>唯一</p></td>
<td><p>与 CodecDescriptionKey 对应的编解码器的唯一说明。</p></td>
</tr>
</tbody>
</table>

