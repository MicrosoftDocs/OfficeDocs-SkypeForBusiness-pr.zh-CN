---
title: PurgeSettings 表 (QoE)
TOCTitle: PurgeSettings 表 (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204788(v=OCS.15)
ms:contentKeyID: 49312422
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# PurgeSettings 表 (QoE)

 

_**上一次修改主题：** 2015-03-09_

PurgeSettings 表包含指定是否（以及何时）将过时的用户体验质量记录从 QoE 数据库中自动删除。请注意，还可以通过运行以下命令从 Microsoft Lync Server 2013 命令行管理程序中获取与清除相关的信息：

    Get-CsQoEConfiguration

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
<th><strong>列</strong></th>
<th><strong>数据类型</strong></th>
<th><strong>键/索引</strong></th>
<th><strong>详细信息</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>QoE 清除设置集合的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>当设置为 True (1) 时，Microsoft Lync Server 2013 将定期从 QoE 数据库中清除过时的记录。将每天在 PurgeHour 设置所指定的时间执行清除。如果设置为 False (0)，则不会从数据库中自动清除记录。默认值为 True。</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>指定将从数据库中清除的 QoE 记录的保留时间（以天为单位）：如果启用了清除，将从数据库中移除高于此值的 QoE 记录。默认值为 60 天。</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>指定将执行数据库清除的本地时间。将采用 24 小时制指定时间，其中 0 表示午夜 (12:00 AM)，23 表示 11:00 PM。请注意，您只能指定小时：允许值 10（指示 10:00 AM），但不允许值 10:30（即 10.5）（指示 10:30 AM）。默认值为 1 (1:00 AM)。</p></td>
</tr>
</tbody>
</table>

