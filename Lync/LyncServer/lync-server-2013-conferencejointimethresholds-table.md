---
title: Lync Server 2013 中的 ConferenceJoinTimeThresholds 表
TOCTitle: Lync Server 2013 中的 ConferenceJoinTimeThresholds 表
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204809(v=OCS.15)
ms:contentKeyID: 49312512
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 ConferenceJoinTimeThresholds 表

 

_**上一次修改主题：** 2015-03-09_

ConferenceJoinTimeThresholds 表包含会议加入时间摘要报告使用的分类边界。会议加入时间摘要报告总结了用户成功加入会议所需的时间；这些时间值都报告为一个平均值，且采用以下类别之一：

  - 少于 2 秒。

  - 2 秒到 5 秒之间。

  - 5 秒到 10 秒之间。

  - 长于 10 秒。

ConferenceJoinTimeThresholds 表包含分类值 2 秒、5 秒和 10 秒。

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
<td><p><strong>ThresholdId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>分类的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>分类的上限。允许的值包括：</p>
<ol>
<li><p>2</p></li>
<li><p>5</p></li>
<li><p>10</p></li>
</ol></td>
</tr>
</tbody>
</table>

